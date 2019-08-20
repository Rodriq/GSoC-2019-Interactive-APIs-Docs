---
method: post
parameters: true
endpoint: users.update
authentication: true
category: users
permalink: /developer-guides/rest-api/users/update/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Update

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

**Note**

- To save `customFields` you must first define the `customFields` in admin panel (Accounts -> Registration -> Custom fields)
- To update the password for the user, "edit-other-user-password" permission must be set accordingly using an administrator account (Administration > Permissions).

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

<!-- | Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `userId` | `BsNr28znDkG8aeo7W` | Required | The id of the user to update. |
| `data.email` | `example@example.com` | Optional | The email address for the user. |
| `data.name` | `Example User` | Optional | The display name of the user. |
| `data.password` | `pass@w0rd` | Optional | The password for the user. |
| `data.username` | `example` | Optional | The username for the user. |
| `data.active` | `false` | Optional <br> Default: `true` | Whether the user is active, which determines if they can login or not. |
| `data.roles` | `['bot']` | Optional <br> Default: `['user']` | The roles the user has assigned to them. |
| `data.joinDefaultChannels` | `false` | Optional <br> Default: `true` | Whether the user should join the default channels. |
| `data.requirePasswordChange` | `true` | Optional <br> Default: `false` | Should the user be required to change their password when they login? |
| `data.sendWelcomeEmail` | `true` | Optional <br> Default: `false` | Should the user get a welcome email? |
| `data.verified` | `true` | Optional <br> Default: `false` | Should the user's email address be verified? |
| `data.customFields` | `{ twitter: '@example' }` | Optional <br> Default: `undefined` | Any custom fields the user should have on their account. | -->

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.update \
     -d '{"userId": "BsNr28znDkG8aeo7W", "data": { "name": "new name", "email": "newemail@user.tld" }}'
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.48.0 | Renamed to `users.update` |
| 0.35.0 | Added as `user.update` |
