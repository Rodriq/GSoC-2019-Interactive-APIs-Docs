---
method: get
parameters: true
endpoint: directory
authentication: true
category: miscellaneous
permalink: /developer-guides/rest-api/miscellaneous/directory/
--- 

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Directory

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}

<!-- A method, that searches by users or channels on all users and channels available on server.
It supports the [Offset, Count, and Sort Query Parameters](../../offset-and-count-and-sort-info/)
along with [Query and Fields Query Parameters](../../query-and-fields-info/).

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/directory` | `yes` | `GET` | -->

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `query` | `{"text": "rocket", "type": "users", "workspace": "local"}` | Required | When `type` is `users` you can send an additional `workspace` field, that can be `local` (default) or `all`. `workspace=all` will work only if [Federation](../../../../administrator-guides/federation) is enabled. |

## Example Call

```bash
curl -G -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
          -H "X-User-Id: hw5DThnhQmxDWnavu" \
          -H "Content-type: application/json" \
          http://localhost:3000/api/v1/directory \
          --data-urlencode 'query={"text": "rocket", "type": "users", "workspace": "local"}'
```

## Example Result

```json
{
    "result": [
        {
            "_id": "jRca8kibJx8NkLJxt",
            "createdAt": "2018-04-13T12:46:26.517Z",
            "emails": [
                {
                    "address": "user.test.1523623548558@rocket.chat",
                    "verified": false
                }
            ],
            "name": "EditedRealNameuser.test.1523623548558",
            "username": "editedusernameuser.test.1523623548558"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Example Call

```bash
curl -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
          -H "X-User-Id: hw5DThnhQmxDWnavu" \
          -H "Content-type: application/json" \
 http://localhost:3000/api/v1/directory?query={"text": "gene", "type": "channels"}&count=1&offset=2
```

## Example Result

```json
{
    "result": [
        {
            "_id": "GENERAL",
            "ts": "2018-05-15T19:10:54.689Z",
            "name": "general",
            "usernames": [
                "rocketchat.internal.admin.test",
                "editedusernameuser.test.1526941091574"
            ]
        }
    ],
    "count": 1,
    "offset": 2,
    "total": 4,
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 1.0.0 | Added `workspace` query param |
| 0.65.0 | Added Pagination fields: `count`, `total`, `offset` |
| 0.64.0 | Added |
