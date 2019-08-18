---
method: get
parameters: false
endpoint: info
authentication: false
category: miscellaneous
permalink: /developer-guides/rest-api/miscellaneous/info/
---

# Info

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath="/api/info" %}

## Example Call

```bash
curl http://localhost:3000/api/info
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath="/api/info" %}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.13.0 | Added |
