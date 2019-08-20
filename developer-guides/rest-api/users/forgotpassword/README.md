---
method: post
parameters: true
endpoint: users.forgotPassword
authentication: true
category: users
permalink: /developer-guides/rest-api/users/forgotpassword/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Forgot Password

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

**Note**

- Please ensure that you have completed the configuration of the Email; otherwise, your users will not receive the mail normally. Accessible from Administration -> Email.

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call - As JSON

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/users.forgotPassword \
      -d '{ "email": "email@rocket.cat" }'
```

## Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.64.0 | Added |

