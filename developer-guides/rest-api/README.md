
# Rocket.Chat REST API

The REST API allows you to control and extend Rocket.Chat with ease.

> **This API is a work in progress, so feel free to test, ask us questions, and submit Pull Requests!**

If you are an end-user and not a dev or a tester, [create a New Feature Request](https://forums.rocket.chat/c/feature-requests) to request new APIs -- and consider [making a donation](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZL94ZE6LGVUSN) to the project.

> All API calls in the documentation are made using `curl`.  However, you are free to use Java / Python / PHP / Golang / Ruby / Swift / Objective-C / Rust / Scala / C# or any other programming languages.

## Production Security Concerns

When calling a production Rocket.Chat server, ensure it is running via HTTPS and has a valid SSL Certificate. The login method requires you to post your username and password in plaintext, which is why we highly suggest only calling the REST login API over HTTPS. Also, few things to note:

- Only call via HTTPS
- Implement a timed authorization token expiration strategy
- Ensure the calling user only has permissions for what they are calling and no more

### Miscellaneous Information

{% include api/render_endpoints.html category="miscellaneous" entry=true %}

### Assets

{% include api/render_endpoints.html category="assets" entry=true %}

### Authentication

{% include api/render_endpoints.html category="authentication" entry=true %}

### Users

{% include api/render_endpoints.html category="users" entry=true %}

### Channels

{% include api/render_endpoints.html category="channels" entry=true %}

### Groups

{% include api/render_endpoints.html category="groups" entry=true %}

### Chat

| Url                                   | Short Description                                                | Details Page                            |
| :------------------------------------ | :--------------------------------------------------------------- | :-------------------------------------- |
| `/api/v1/chat.delete`                 | Deletes an existing chat message.                                | [Link](chat/delete/)                    |
| `/api/v1/chat.followMessage`          | Follows an existing chat message.                                | [Link](chat/followmessage/)             |
| `/api/v1/chat.getDeletedMessages`     | Retrieves the deleted messages since specific date.              | [Link](chat/getdeletedmessages/)        |
| `/api/v1/chat.getMessage`             | Retrieves a single chat message.                                 | [Link](chat/getmessage/)                |
| `/api/v1/chat.getMessageReadReceipts` | Retrieves message read receipts.                                 | [Link](chat/getmessagereadreceipts/)    |
| `/api/v1/chat.getThreadMessages`      | Retrieves thread's messages.                                     | [Link](chat/getthreadmessages/)         |
| `/api/v1/chat.getThreadsList`         | Retrieves channel's threads.                                     | [Link](chat/getthreadslist/)            |
| `/api/v1/chat.ignoreUser`             | Ignores an user from a chat.                                     | [Link](chat/ignoreuser/)                |
| `/api/v1/chat.pinMessage`             | Pins a chat message to the message's channel.                    | [Link](chat/pinmessage/)                |
| `/api/v1/chat.postMessage`            | Posts a new chat message.                                        | [Link](chat/postmessage/)               |
| `/api/v1/chat.react`                  | Sets/unsets the user's reaction to an existing chat message.     | [Link](chat/react/)                     |
| `/api/v1/chat.reportMessage`          | Reports a message.                                               | [Link](chat/reportmessage/)             |
| `/api/v1/chat.search`                 | Search for messages in a channel.                                | [Link](chat/search/)                    |
| `/api/v1/chat.starMessage`            | Stars a chat message for the authenticated user.                 | [Link](chat/starmessage/)               |
| `/api/v1/chat.sendMessage`            | Send new chat message.                                           | [Link](chat/sendmessage/)               |
| `/api/v1/chat.syncThreadMessages`     | Retrieves synced thread's messages.                              | [Link](chat/syncthreadmessages/)        |
| `/api/v1/chat.syncThreadsList`        | Retrieves thread's synced channel threads.                       | [Link](chat/syncthreadslist/)           |
| `/api/v1/chat.unfollowMessage`        | Unfollows an existing chat message.                              | [Link](chat/unfollowmessage/)           |
| `/api/v1/chat.unPinMessage`           | Removes the pinned status of the provided chat message.          | [Link](chat/unpinmessage/)              |
| `/api/v1/chat.unStarMessage`          | Removes the star on the chat message for the authenticated user. | [Link](chat/unstarmessage/)             |
| `/api/v1/chat.update`                 | Updates the text of the chat message.                            | [Link](chat/update/)                    |

### IM

| Url                          | Short Description                                             | Details Page                |
| :--------------------------- | :------------------------------------------------------------ | :-------------------------- |
| `/api/v1/im.close`           | Removes a direct message from the list of direct messages.    | [Link](im/close/)           |
| `/api/v1/im.counters`        | Gets counters of direct messages.                             | [Link](im/counters/)        |
| `/api/v1/im.create`          | Create a direct message session with another user.            | [Link](im/create/)          |
| `/api/v1/im.history`         | Retrieves the messages from a direct message.                 | [Link](im/history/)         |
| `/api/v1/im.files`           | Retrieves a list of files from a direct message.              | [Link](im/files/)           |
| `/api/v1/im.members`         | Retrieves the users of participants of a direct message.      | [Link](im/members/)         |
| `/api/v1/im.messages`        | Retrieves the messages from specific direct message.          | [Link](im/messages/)        |
| `/api/v1/im.messages.others` | Retrieves the messages from any direct message in the server. | [Link](im/messages-others/) |
| `/api/v1/im.list`            | List the direct messages the caller is part of.               | [Link](im/list/)            |
| `/api/v1/im.list.everyone`   | List all direct message the caller in the server.             | [Link](im/list-everyone/)   |
| `/api/v1/im.open`            | Adds the direct message back to the list of direct messages.  | [Link](im/open/)            |
| `/api/v1/im.setTopic`        | Sets a direct message topic.                                  | [Link](im/settopic/)        |

### Integrations

| Url                            | Short Description                                             | Details Page                |
| :----------------------------- | :------------------------------------------------------------ | :-------------------------- |
| `/api/v1/integrations.create`  | Creates an integration.                                       | [Link](integration/create/) |
| `/api/v1/integrations.history` | Lists all history of the specified integration.               | [Link](integration/history/)|
| `/api/v1/integrations.list`    | Lists all of the integrations.                                | [Link](integration/list/)   |
| `/api/v1/integrations.remove`  | Removes an integration.                                       | [Link](integration/remove/) |

### Livechat

| Url                              | Short Description                                             | Details Page                     |
| :------------------------------- | :------------------------------------------------------------ | :------------------------------- |
| `/api/v1/livechat/inquiries.list`| Retrieves a list of open inquiries.                           | [Link](livechat/inquiries-list/) |
| `/api/v1/livechat/inquiries.take`| Take an open inquiry.                                         | [Link](livechat/inquiries-take/) |

### Permissions

| Url                             | Short Description                | Details Page                 |
| :------------------------------ | :------------------------------- | :--------------------------  |
| `/api/v1/permissions.listAll`   | Lists permissions on the server. | [Link](permissions/list-all/)|
| `/api/v1/permissions.update`    | Edits permissions on the server. | [Link](permissions/update/)  |

### Roles

| Url                          | Short Description                | Details Page                |
| :--------------------------- | :------------------------------- | :-------------------------- |
| `/api/v1/roles.create`   | Create a new role in the system. | [Link](roles/create/)   |
| `/api/v1/roles.list` | Gets all the roles in the system. | [Link](roles/list/) |
| `/api/v1/roles.addUserToRole` | Assign a role to an user. | [Link](roles/addusertorole/) |

### Push Token

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/push.token`              | `POST`    | Saves push token.                 | [Link](push/push-token/)       |
| `/api/v1/push.token`              | `DELETE`  | Removes push token.               | [Link](push/deletepushtoken/)  |

### Rooms

{% include api/render_endpoints.html category="rooms" entry=true %}

### Command Methods

| Url                     | Short Description                              | Details Page           |
| :---------------------- | :--------------------------------------------- | :--------------------- |
| `/api/v1/commands.get`  | Get specification of the slash command.        | [Link](commands/get/)  |
| `/api/v1/commands.list` | Lists all available slash commands.            | [Link](commands/list/) |
| `/api/v1/commands.run`  | Execute a slash command in the specified room. | [Link](commands/run/)  |

### Emoji Custom

| Url                             | Short Description                              | Details Page                 |
| :------------------------------ | :--------------------------------------------- | :--------------------------- |
| `/api/v1/emoji-custom.list`     | List the custom emojis available.              | [Link](emoji-custom/list/)   |
| `/api/v1/emoji-custom.create`   | Create new custom emoji.                       | [Link](emoji-custom/create/) |
| `/api/v1/emoji-custom.delete`   | Delete an existent custom emoji.               | [Link](emoji-custom/delete/) |
| `/api/v1/emoji-custom.update`   | Update an existent custom emoji.               | [Link](emoji-custom/update/) |

### Settings

| Url                               | Method | Short Description                                   | Details Page                                    |
| :-------------------------------- | :----- | :-------------------------------------------------- | :---------------------------------------------- |
| `/api/v1/settings`                | `GET`  | Lists all private settings.                         | [Link](settings/get/)                           |
| `/api/v1/settings.public`         | `GET`  | Lists all public settings.                          | [Link](settings/public/)                    |
| `/api/v1/settings.oauth`          | `GET`  | Return list of all available oauth services.        | [Link](settings/oauth/) |
| `/api/v1/service.configurations`  | `GET`  | Lists all service configurations.                   | [Link](settings/service-configuration/)    |
| `/api/v1/settings/:_id`           | `GET`  | Gets a setting.                                     | [Link](settings/get-by-id/)                     |
| `/api/v1/settings/:_id`           | `POST` | Updates a setting.                                  | [Link](settings/update/)                        |

### Subscriptions

| Url                               | Method  | Short Description                  | Details Page                      |
| :-------------------------------- | :------ | :--------------------------------- | :-------------------------------- |
| `/api/v1/subscriptions.get`       |  `GET`  | Get all subscriptions.             | [Link](subscriptions/get/)                      |
| `/api/v1/subscriptions.getOne`    | `GET`   | Get the subscription by room Id.   | [Link](subscriptions/getone/)     |
| `/api/v1/subscriptions.read`      | `POST`  |  Mark a room as read.              | [Link](subscriptions/read/)       |
| `/api/v1/subscriptions.unread`    | `POST`  | Mark messages as unread.           | [Link](subscriptions/unread/)     |

### Video Conference

| Url                                              | Short Description                                           | Details Page                                   |
| :----------------------------------------------- | :---------------------------------------------------------- | :-----------------------------------------     |
| `/api/v1/video-conference/jitsi.update-timeout`  | Updates the timeout of Jitsi video conference in a channel. | [Link](video-conference/jitsi-update-timeout)  |

## Language specific wrappers

### Java

- [rocket-chat-rest-client](https://github.com/baloise/rocket-chat-rest-client)

### PHP

- [rocket-chat-rest-client](https://github.com/Fab1en/rocket-chat-rest-client)

### Python

- [rocketchat_API](https://github.com/jadolg/rocketchat_API)

### Ruby

- [rocketchat-ruby](https://github.com/abrom/rocketchat-ruby)

### Clojure

- [rocketchat-clojure](https://github.com/MalloZup/missile)
