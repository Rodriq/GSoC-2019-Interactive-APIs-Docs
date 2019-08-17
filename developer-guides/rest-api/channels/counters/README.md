---
method: get
parameters: true
endpoint: channels.counters
authentication: true
category: channels
permalink: /developer-guides/rest-api/channels/counters/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Channel Counters

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Payload

One of roomId or roomName is required.
{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Example Call

```bash
curl -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
     -H "X-User-Id: ew28FnZqipDpvKw3R" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/channels.counters?roomId=GENERAL
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

where:

joined - boolean flag that shows that user is joined the room or not
members - count of current room members
unreads - count of unread messages for specified user (calling user or provided userId)
unreadsFrom - start date-time of unread interval for specified user
msgs - count of messages in the room
latest - end date-time of unread interval for specified user (or date-time of last posted message)
userMentions - count of user mentions in messages
```
## Change Log

| Version | Description |
| :--- | :--- |
| 0.65.0 | Added |
