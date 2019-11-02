---
method: post
parameters: true
endpoint: rooms.saveNotification
authentication: true
category: rooms
permalink: /developer-guides/rest-api/rooms/savenotification/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Rooms save notification POST

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `5of4weEXaH7yncxz9` | Required | The channel's id |
| `notifications.desktopNotifications` | `nothing` | Optional: 'nothing', 'all', 'mentions', 'default' | The value for desktop notifications |
| `notifications.disableNotifications` | `'0'` | Optional: '0' or '1' | The value to disable/enable channel's notifications. |
| `notifications.emailNotifications` | `nothing` | Optional: 'nothing', 'all', 'mentions', 'default' | The value for email notifications. |
| `notifications.audioNotifications` | `nothing` | Optional: 'nothing', 'all', 'mentions', 'default' | The value for audio notifications. |
| `notifications.mobilePushNotifications` | `nothing` | Optional: 'nothing', 'all', 'mentions', 'default' | The value for mobile push notifications. |
| `notifications.audioNotificationValue` | `beep` | Optional | The value for audio notification sound. |
| `notifications.desktopNotificationDuration` | `'0'` | Optional | The value for desktop notification duration. |
| `notifications.unreadAlert` | `nothing` | Optional: 'nothing', 'all', 'mentions', 'default' | The value for unread alerts notifications. |
| `notifications.hideUnreadStatus` | `'0'` | Optional: '0' or '1' | The value to disable/enable number of unread messages. |

## Example payload

```json
{
    "roomId": "5of4weEXaH7yncxz9",
    "notifications" :{
        "desktopNotifications": "all",
        "disableNotifications": "0",
        "emailNotifications": "nothing",
        "audioNotificationValue": "beep",
        "desktopNotificationDuration": "2",
        "audioNotifications": "all",
        "unreadAlert": "nothing",
        "hideUnreadStatus": "all",
        "mobilePushNotifications": "mentions"
    }
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.saveNotification \
     -d '{"roomId": "5of4weEXaH7yncxz9", "notifications" :{ "desktopNotifications": "all", "disableNotifications": "0", \
     "emailNotifications": "nothing", "audioNotificationValue": "beep", "desktopNotificationDuration": "2", "audioNotifications": "all", \
       "unreadAlert": "nothing", "hideUnreadStatus": "all", "mobilePushNotifications": "mentions"} }'
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

## Change Log

| Version | Description |
| :--- | :--- |
| 0.63.0 | Added |
