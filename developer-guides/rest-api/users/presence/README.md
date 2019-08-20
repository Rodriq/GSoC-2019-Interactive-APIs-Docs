---
method: get
parameters: true
endpoint: users.presence
authentication: true
category: users
permalink: /developer-guides/rest-api/users/presence/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Users Presence

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Query Parameters

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## All users presence example call

If you don't pass `from` parameter, you'll get a list of all users presence and the result will
have a `full` field with value `true` indicating that.

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.presence
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Users presence changed after period example call

If you pass `from` parameter, you'll get only a list users presence which have changed after the time
of `from` parameter. The `full` result field will then be `false`, indicating it's a partial result.

If the value of `from` parameter is older than 10 minutes, the server will reply with a **full** result set.

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.presence?from=2019-05-22T12:11:45.392Z
```

## Example Result

```json
{
   "users":[
      {
         "_id":"rocket.cat",
         "name":"Rocket.Cat",
         "username":"rocket.cat",
         "status":"online",
         "utcOffset":0
      },
      {
         "_id":"rocketchat.internal.admin.test",
         "name":"RocketChat Internal Admin Test",
         "username":"rocketchat.internal.admin.test",
         "status":"online",
         "utcOffset":-2
      }
   ],
   "full": false,
   "success":true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 1.1.0 | Added |
