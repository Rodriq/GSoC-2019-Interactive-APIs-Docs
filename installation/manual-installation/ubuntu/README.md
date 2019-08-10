# Rocket.Chat in Ubuntu

## Recommended Fastest Server Install via Snaps

Snaps are the easiest way for you to get your server up and running on all supported Linux distributions (Ubuntu, etc).

Find out more information about installing using snaps [here](snaps/)

If you would like to enable TLS on your site like this `https://yoursite.com` when using the snap, please see [here](snaps/autossl/)

## Manual install

This installation guide was tested in the following environment:

- Rocket.Chat 1.0.2
- OS: Ubuntu 18.04 LTS and Ubuntu 19.04
- Mongodb 4.0.9
- NodeJS 8.11.4

## Install necessary dependency packages

Update package list and configure apt to install the official MongoDB packages with the following repository file:

```bash
sudo apt-get -y update
```

```bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
```

```bash
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
```

Configure Node.js to be installed via package manager:

```bash
sudo apt-get -y update && sudo apt-get install -y curl && curl -sL https://deb.nodesource.com/setup_8.x | sudo bash -
```

Install build tools, MongoDB, nodejs and graphicsmagick:

```bash
sudo apt-get install -y build-essential mongodb-org nodejs graphicsmagick
```

Only for Ubuntu 19.04 install npm:

```bash
sudo apt-get install -y npm
```

Using npm install inherits and n, and the node version requiere by Rocket.Chat:

```bash
sudo npm install -g inherits n && sudo n 8.11.4
```

## Install Rocket.Chat

Download the latest Rocket.Chat version:

```bash
curl -L https://releases.rocket.chat/latest/download -o /tmp/rocket.chat.tgz
```

```bash
tar -xzf /tmp/rocket.chat.tgz -C /tmp
```

Install (this guide uses /opt but feel free to choose a different directory):

```bash
cd /tmp/bundle/programs/server && npm install
```

```bash
sudo mv /tmp/bundle /opt/Rocket.Chat
```

## Configure the Rocket.Chat service

Add the rocketchat user, set the right permissions on the Rocket.Chat folder and create the Rocket.Chat service file:

```bash
sudo useradd -M rocketchat && sudo usermod -L rocketchat
```

```bash
sudo chown -R rocketchat:rocketchat /opt/Rocket.Chat
```

```bash
cat << EOF |sudo tee -a /lib/systemd/system/rocketchat.service
[Unit]
Description=The Rocket.Chat server
After=network.target remote-fs.target nss-lookup.target nginx.target mongod.target
[Service]
ExecStart=/usr/local/bin/node /opt/Rocket.Chat/main.js
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=rocketchat
User=rocketchat
Environment=MONGO_URL=mongodb://localhost:27017/rocketchat?replicaSet=rs01 MONGO_OPLOG_URL=mongodb://localhost:27017/local?replicaSet=rs01 ROOT_URL=http://localhost:3000/ PORT=3000
[Install]
WantedBy=multi-user.target
EOF
```

Open the Rocket.Chat service file just created (`/lib/systemd/system/rocketchat.service`) using sudo and your favourite text editor, and change the ROOT_URL environmental variable to reflect the URL you want to use for accessing the server (optionally change MONGO_URL, MONGO_OPLOG_URL and PORT):

```bash
MONGO_URL=mongodb://localhost:27017/rocketchat?replicaSet=rs01
MONGO_OPLOG_URL=mongodb://localhost:27017/local?replicaSet=rs01
ROOT_URL=http://your-host-name.com-as-accessed-from-internet:3000
PORT=3000
```

Setup storage engine and replication for MongoDB (mandatory for versions > 1), and enable and start MongoDB and Rocket.Chat:

```bash
sudo sed -i "s/^#  engine:/  engine: mmapv1/"  /etc/mongod.conf
```

```bash
sudo sed -i "s/^#replication:/replication:\n  replSetName: rs01/" /etc/mongod.conf
```

```bash
sudo systemctl enable mongod && sudo systemctl start mongod
```

```bash
mongo --eval "printjson(rs.initiate())"
```

```bash
sudo systemctl enable rocketchat && sudo systemctl start rocketchat
```

## Optional configurations

[Configure firewall rule](../optional-configurations)
[Configure a HTTP reverse proxy to access Rocket.Chat server](../configuring-ssl-reverse-proxy/)
[Configure mongo access control]
[Configure production values for mongodb]

## Configure your Rocket.Chat server

Open a web browser and access the configured ROOT_URL (`http://your-host-name.com-as-accessed-from-internet:3000`), follow the configuration steps to set an admin account and your organization and server info.
