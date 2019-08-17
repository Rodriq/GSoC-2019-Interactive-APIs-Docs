---
method: get
parameters: false
endpoint: me
authentication: true
category: authentication
permalink: /developer-guides/rest-api/authentication/me/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Me

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/me
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

**Note**

- The `customFields` will not be returned if it does not exist on the server.

## Change Log

| Version | Description |
| :--- | :--- |
| 1.0.0 | Added `avatarUrl` property to response |
| 0.68.0 | Added `customFields` property. |
| 0.48.0 | Added |