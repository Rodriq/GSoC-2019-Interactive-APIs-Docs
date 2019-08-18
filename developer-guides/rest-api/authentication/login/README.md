---
method: post
parameters: true
endpoint: login
authentication: false
category: authentication
permalink: /developer-guides/rest-api/authentication/login/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Login

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method fullPath=fullPath %}

**Notes**

- **You will need to provide the `authToken` and `userId` for any of the authenticated methods.** <br/>
- **If your user has two-factor(2FA) authentication enabled, you must send a request like [this](#example-call---when-two-factor2fa-authentication-is-enabled).** <br/>
- **If LDAP authentication is enabled, you must maintain the login in the same way as you normally do. Similarly if 2FA is enabled for an LDAP user. Everything stays the same.** <br/>

## Example Call - As Form Data

```bash
curl http://localhost:3000/api/v1/login \
-d "user=myusername&password=mypassword"
```

```bash
curl http://localhost:3000/api/v1/login \
-d "user=my@email.com&password=mypassword"
```

## Example Call - As JSON

```bash
curl -H "Content-type:application/json" \
http://localhost:3000/api/v1/login \
-d '{ "user": "myusername", "password": "mypassword" }'
```

```bash
curl -H "Content-type:application/json" \
http://localhost:3000/api/v1/login \
-d '{ "user": "my@email.com", "password": "mypassword" }'
```

## Example Call - When two-factor(2FA) authentication is enabled

```bash
curl -H "Content-type:application/json" \
http://localhost:3000/api/v1/login \
-d '{ "user": "myusername", "password": "mypassword", "code": "224610" }'
```

```bash
curl -H "Content-type:application/json" \
http://localhost:3000/api/v1/login \
-d '{ "user": "my@email.com", "password": "mypassword", "code": "224610" }'
```

## Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Change Log

| Version | Description |
| :--- | :--- |
| 1.0.0 | Added `avatarUrl` property to response |
| 0.64.0 | Added `me` property to response |
| 0.60.0 | Added |
