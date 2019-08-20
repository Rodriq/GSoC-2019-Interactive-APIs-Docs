---
method: get
parameters: true
endpoint: users.list
authentication: true
category: users
permalink: /developer-guides/rest-api/users/list/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# List

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Query Parameters

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Other Users Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.list
```

## Example Result Regular User Callee

```json
{
  "users": [
    {
      "_id": "nSYqWzZ4GsKTX4dyK",
      "type": "user",
      "status": "offline",
      "active": true,
      "name": "Example User",
      "utcOffset": 0,
      "username": "example"
    },
    {
      ...
    }
  ],
  "count": 10,
  "offset": 0,
  "total": 10,
  "success": true
}
```

## Example Result Admin Callee

```json
{
  "users": [
    {
      "_id": "nSYqWzZ4GsKTX4dyK",
      "createdAt": "2016-12-07T15:47:46.861Z",
      "services": {
        "password": {
          "bcrypt": ...
        },
        "email": {
          "verificationTokens": [
            {
              "token": "...",
              "address": "example@example.com",
              "when": "2016-12-07T15:47:46.930Z"
            }
          ]
        },
        "resume": {
          "loginTokens": [
            {
              "when": "2016-12-07T15:47:47.334Z",
              "hashedToken": "..."
            }
          ]
        }
      },
      "emails": [
        {
          "address": "example@example.com",
          "verified": true
        }
      ],
      "type": "user",
      "status": "offline",
      "active": true,
      "roles": [
        "user"
      ],
      "name": "Example User",
      "lastLogin": "2016-12-08T00:22:15.167Z",
      "statusConnection": "offline",
      "utcOffset": 0,
      "username": "example"
    },
    {
      ...
    }
  ],
  "count": 3,
  "offset": 2,
  "total": 10,
  "success": true
}
```

# Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.49.0 | Count and offset query parameters supported. |
| 0.35.0 | Added |
