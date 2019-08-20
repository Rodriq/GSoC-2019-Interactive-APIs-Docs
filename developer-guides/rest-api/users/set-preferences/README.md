---
method: post
parameters: true
endpoint: users.setPreferences
authentication: true
category: users
permalink: /developer-guides/rest-api/users/setpreferences/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Set Preferences

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

<!-- | Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `userId`                          | `BsNr28znDkG8aeo7W` | Required | The id of the user.              |
| `data.newRoomNotification`        | `test`              | Required | New room notification.           |
| `data.newMessageNotification`     | `test`              | Required | New message notification.        |
| `data.useEmojis`                  | `true`              | Required | User can use emojis.             |
| `data.convertAsciiEmoji`          | `true`              | Required | Convert ascII emojis.            |
| `data.saveMobileBandwidth`        | `true`              | Required | Save mobile bandwidth.            |
| `data.collapseMediaByDefault`     | `true`              | Required | Collapse media by default.       |
| `data.autoImageLoad`              | `true`              | Required | Image load automatically.        |
| `data.emailNotificationMode`      | `test`              | Required | Email notification mode.         |
| `data.roomsListExhibitionMode`    | `test`              | Required | Rooms list exhibition mode.      |
| `data.unreadAlert`                | `true`              | Required | Unread Alert.                    |
| `data.notificationsSoundVolume`   | `100`               | Required | Volume of notification sound.    |
| `data.desktopNotifications`       | `test`              | Required | Desktop notifications.           |
| `data.mobileNotifications`        | `test`              | Required | Mobile notifications.            |
| `data.enableAutoAway`             | `true`              | Required | Enable auto away.                |
| `data.highlights`                 | `[]`                | Required | Highlights.                      |
| `data.desktopNotificationDuration`| `100`               | Required | Duration of desktop notification.|
| `data.viewMode`                   | `0`                 | Required | View mode.                       |
| `data.hideUsernames`              | `false`             | Required | Hide usernames.                  |
| `data.hideRoles`                  | `false`             | Required | Hide user roles.                 |
| `data.hideAvatars`                | `false`             | Required | Hide avatars.                    |
| `data.sendOnEnter`                | `test`              | Required | Send message on enter.           |
| `data.roomCounterSidebar`         | `true`              | Required | Display room counter on sidebar. |
| `data.language`                   | `pt-BR`             | Required | Language.                        |
| `data.sidebarShowFavorites`       | `true`              | Optional | Show favorites on sidebar.       |
| `data.sidebarShowUnread`          | `true`              | Optional | Show unread on sidebar.          |
| `data.sidebarSortby`              | `test`              | Optional | Show sort by.                    |
| `data.sidebarViewMode`            | `test`              | Optional | Show view mode.                  |
| `data.sidebarHideAvatar`          | `true`              | Optional | Show avatar on hide bar.         |
| `data.groupByType`                | `true`              | Optional | Group channels by type.          |
| `data.muteFocusedConversations`   | `true`              | Optional | Mute focused conversations.      | -->

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.setPreferences \
     -d '{ "userId": "BsNr28znDkG8aeo7W", "data": { } }'
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}
