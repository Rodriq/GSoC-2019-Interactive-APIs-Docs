---
method: get
parameters: false
endpoint: me
authentication: true
category: authentication
permalink: /developer-guides/rest-api/authentication/me/
--- 

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Me

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

<!-- Quick information about the authenticated user.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- | :--- |
| `/api/v1/me` | `yes` | `GET` | -->

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/me
```

## Example Result

```json
{
  "_id": "aobEdbYhXfu5hkeqG",
  "name": "Example User",
  "emails": [
    {
      "address": "example@example.com",
      "verified": true
    }
  ],
  "status": "offline",
  "statusConnection": "offline",
  "username": "example",
  "utcOffset": 0,
  "active": true,
  "roles": [
      "user",
      "admin"
  ],
  "settings": {
        "preferences": {
            "enableAutoAway": false,
            "idleTimeoutLimit": 300,
            "desktopNotificationDuration": 0,
            "audioNotifications": "mentions",
            "desktopNotifications": "mentions",
            "mobileNotifications": "mentions",
            "unreadAlert": true,
            "useEmojis": true,
            "convertAsciiEmoji": true,
            "autoImageLoad": true,
            "saveMobileBandwidth": true,
            "collapseMediaByDefault": false,
            "hideUsernames": false,
            "hideRoles": false,
            "hideFlexTab": false,
            "hideAvatars": false,
            "roomsListExhibitionMode": "category",
            "sidebarViewMode": "medium",
            "sidebarHideAvatar": false,
            "sidebarShowUnread": false,
            "sidebarShowFavorites": true,
            "sendOnEnter": "normal",
            "messageViewMode": 0,
            "emailNotificationMode": "all",
            "roomCounterSidebar": false,
            "newRoomNotification": "door",
            "newMessageNotification": "chime",
            "muteFocusedConversations": true,
            "notificationsSoundVolume": 100
        }
  },
    "customFields": {
        "twitter": "@userstwi"
    },
  "avatarUrl": "http://localhost:3000/avatar/test",
  "customFields": {
      "twitter": "@userstwi"
  },
  "success": true
}
```

**Note**

- The `customFields` will not be returned if it does not exist on the server.

## Change Log

| Version | Description |
| :--- | :--- |
| 1.0.0 | Added `avatarUrl` property to response |
| 0.68.0 | Added `customFields` property. |
| 0.48.0 | Added |