---
method: post
parameters: true
endpoint: users.updateOwnBasicInfo
authentication: true
category: users
permalink: /developer-guides/rest-api/users/updateownbasicinfo/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Update own basic information

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

Note that to update the password or email for the user you must send `currentPassword` property encrypted in SHA256 together in payload.

**WARNING:** This API does not work when the server contains custom fields. There's a bug report [here](https://github.com/RocketChat/Rocket.Chat/issues/11154) related to that.

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

<!-- | Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `data.email` | `example@example.com` | Optional | The email address for the user. |
| `data.name` | `Example User` | Optional | The display name of the user. |
| `data.username` | `example` | Optional | The username for the user. |
| `data.currentPassword` | `5994471abb01112afcc18159f6cc74b4f511b99806da59b3caf5a9c173cacfc5@w0rd` | Optional | The password for the user encrypted in SHA256. |
| `data.newPassword` | `passw0rd` | Optional | The new password for the user |
| `data.customFields` | `{ twitter: '@example' }` | Optional <br> Default: `undefined` | Any custom fields the user should have on their account. | -->

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.updateOwnBasicInfo \
     -d '"data" :{"email": "rocket.cat@rocket.chat", "newPassword": "passw0rd",
     "currentPassword": "5994471abb01112afcc18159f6cc74b4f511b99806da59b3caf5a9c173cacfc5",
      "username": "rocket.cat", name": "Example user" }'
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.62.2 | Added as `user.updateOwnBasicInfo` |
