---
method: get
parameters: true
endpoint: users.getAvatar
authentication: false
category: users
permalink: /developer-guides/rest-api/users/getavatar/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Get Avatar

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call - Via userId

```bash
curl http://localhost:3000/api/v1/users.getAvatar?userId=BsNr28znDkG8aeo7W
```

## Example Result

```
http://localhost:3000/avatar/bobsmith
```

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

_N.B. the response is a 307 temporary redirect_

## Change Log

| Version | Description |
| :------ | :---------- |
| 0.50.0  | Added       |
