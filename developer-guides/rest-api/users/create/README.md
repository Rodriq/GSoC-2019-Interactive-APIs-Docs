---
method: post
parameters: true
endpoint: users.create
authentication: true
category: users
permalink: /developer-guides/rest-api/users/create/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Create

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

**Note**

- To save `customFields` you must first define the `customFields` in admin panel (Accounts -> Registration -> Custom fields).

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.create \
     -d '{"name": "name", "email": "email@user.tld", "password": "anypassyouwant", "username": "uniqueusername"}'
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

**Note**

- The `customFields` will not be returned if it does not exist on the server.

## Change Log

| Version | Description |
| :--- | :--- |
| 0.48.0 | `role` property is now `roles` which is an array of strings for the roles to create the user with. |
| 0.45.0 | Users created via this now join the default channels. |
| 0.40.0 | Added |
