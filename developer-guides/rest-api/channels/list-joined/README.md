---
method: get
parameters: true
endpoint: channels.list.joined
authentication: true
category: channels
permalink: /developer-guides/rest-api/channels/list-joined/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Channel List Joined

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/channels.list.joined
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Query Example Call

This example shows a list of Direct Messages' Rooms filtered by "customFields.field1" ended with "5" using a regular expression.

```bash
curl -H "X-Auth-Token: OKoJelLu8rYtbyc3c5YtTwxIE-UvT1FzWv9cdq1XPI1" \
     -H "X-User-Id: hw5DThnhQmxDWnavu" \
     http://localhost:3000/api/v1/channels.list.joined?query=%7B%20%22name%22%3A%20%7B%20%22%24regex%22%3A%20%22al%24%22%20%7D%20%7D
```

## Query Example Result

```json
{
    "channels": [
        {
            "_id": "GENERAL",
            "ts": "2018-01-21T20:58:41.142Z",
            "t": "c",
            "name": "general",
            "msgs": 1,
            "default": true,
            "_updatedAt": "2018-01-21T21:03:43.736Z",
            "username": "user2"
        }
    ],
    "offset": 0,
    "count": 1,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.62.0 | Add 'query' parameter support. |
| 0.49.0 | Count and offset query parameters supported. |
| 0.48.0 | Added |
