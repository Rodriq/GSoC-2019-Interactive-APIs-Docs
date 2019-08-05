---
method: get
parameters: true
endpoint: channels.files
authentication: true
category: channels
permalink: /developer-guides/rest-api/channels/files/
---

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Channel Files

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

<!-- Retrieves the files from a channel. It supports the [Offset, Count, and Sort Query Parameters](../../offset-and-count-and-sort-info/) along with [Query and Fields Query Parameters](../../query-and-fields-info/).

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/channels.files` | `yes` | `GET` | -->

## Query Parameters

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

<!-- | Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` <br><br> `roomName` | `ByehQjC44FwMeiLbX` <br><br> `test` | <br> Required | The room id. <br><br> The room name.   | -->

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/channels.files?roomId=ByehQjC44FwMeiLbX
```

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/channels.files?roomName=test
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

<!-- ```json
{
    "files": [
        {
            "_id": "S78TNnvaWGwdYRaCD",
            "name": "images.jpeg",
            "size": 9778,
            "type": "image/jpeg",
            "rid": "GENERAL",
            "description": "",
            "store": "GridFS:Uploads",
            "complete": true,
            "uploading": false,
            "extension": "jpeg",
            "progress": 1,
            "user": {
                "_id": "ksKsKmrjvxzkzxkww",
                "username": "rocket.cat",
                "name": "Rocket Cat"
            },
            "_updatedAt": "2018-03-08T14:47:37.003Z",
            "instanceId": "uZG54xuoKauKHykbQ",
            "etag": "jPaviS9qG22xC5sDC",
            "path": "/ufs/GridFS:Uploads/S78TNnvaWGwdYRaCD/images.jpeg",
            "token": "28cAb868d9",
            "uploadedAt": "2018-03-08T14:47:37.295Z",
            "url": "/ufs/GridFS:Uploads/S78TNnvaWGwdYRaCD/images.jpeg"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
``` -->

## Change Log

| Version | Description |
| :--- | :--- |
| 0.64.0 | Change `userId` to `user` object in response |
| 0.59.0 | Added |
