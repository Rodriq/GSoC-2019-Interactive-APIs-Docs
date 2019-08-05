---
method: post
parameters: true
endpoint: channels.removeLeader
authentication: true
category: channels
permalink: /developer-guides/rest-api/channels/removeleader/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Channel Remove Leader

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/channels.removeLeader \
     -d '{"roomId": "ByehQjC44FwMeiLbX", "userId": "oCHkav5Zf6vmpu2W2"}'
```

## Success Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Bad Request Example Result

If the user is not a leader, will return a `400 bad request` status.

```json
{
    "success": false,
    "error": "User is not a leader [error-user-not-leader]",
    "errorType": "error-user-not-leader"
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.75.0 | Added. |
