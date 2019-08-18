---
method: get
parameters: true
endpoint: statistics.list
authentication: true
category: miscellaneous
permalink: /developer-guides/rest-api/miscellaneous/statistics-list/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Statistics List

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Query Parameters

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method fullPath=fullPath %}

## Example Call

A request below performs a statistic search for a server instance with `_id: v3D4mvobwfznKozH8` except response fields like `os`, `migration`, `deploy`, `proces`.

```bash
curl -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
     -H "X-User-Id: ew28FnZqipDpvKw3R" \
     "http://localhost:3000/api/v1/statistics.list?query=%7B%22_id%22%3A%22v3D4mvobwfznKozH8%22%7D&fields=%7B%22os%22%3A0%2C%22migration%22%3A0%2C%22deploy%22%3A0%2C%22process%22%3A0%7D"
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.51.0 | Added |
