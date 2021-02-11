---
method: post
parameters: true
endpoint: rooms.cleanHistory
authentication: true
category: rooms
permalink: /developer-guides/rest-api/rooms/cleanhistory/
redirect_from:
   - /developer-guides/rest-api/channels/cleanhistory
   - /developer-guides/rest-api/channels/cleanhistory/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}


# Rooms Clean History

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.cleanHistory \
     -d '{ "roomId": "roomId", "latest": "2016-12-09T13:42:25.304Z", "oldest": "2016-08-30T13:42:25.304Z" }'
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.64.0 | Added |
| 0.67.0 | Added fields `limit`, `excludePinned`, `filesOnly` and `users` |
