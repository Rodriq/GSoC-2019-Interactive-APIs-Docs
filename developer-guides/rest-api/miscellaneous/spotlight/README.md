---
method: get
parameters: true
endpoint: spotlight
authentication: true
category: miscellaneous
permalink: /developer-guides/rest-api/miscellaneous/spotlight/
redirect_from:
  - /developer-guides/rest-api/spotlight
  - /developer-guides/rest-api/spotlight/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Spotlight

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Query Parameters

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method fullPath=fullPath %}

## Example Call

```bash
curl -H "X-Auth-Token: 6eWs4ECxUITYYoZ_bAYK5OE2srkxAepQqQA1cGGv3jK" \
     -H "X-User-Id: hvzu8z6mHFigiXy6Y" \
     http://localhost:3000/api/v1/spotlight?query=foobar
```

## Example Call

```bash
curl -H "X-Auth-Token: 6eWs4ECxUITYYoZ_bAYK5OE2srkxAepQqQA1cGGv3jK" \
     -H "X-User-Id: hvzu8z6mHFigiXy6Y" \
     http://localhost:3000/api/v1/spotlight?query=@foobar
```

## Example Call

```bash
curl -H "X-Auth-Token: 6eWs4ECxUITYYoZ_bAYK5OE2srkxAepQqQA1cGGv3jK" \
     -H "X-User-Id: hvzu8z6mHFigiXy6Y" \
     http://localhost:3000/api/v1/spotlight?query=#foobar
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.64.0 | Added support to '#' and '@' searches, for channels and users respectively. |
| 0.61.0 | Added. |
