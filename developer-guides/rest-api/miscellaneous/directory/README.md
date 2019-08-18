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

## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method fullPath=fullPath %}

## Example Call

```bash
curl -G -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
          -H "X-User-Id: hw5DThnhQmxDWnavu" \
          -H "Content-type: application/json" \
          http://localhost:3000/api/v1/directory \
          --data-urlencode 'query={"text": "rocket", "type": "users", "workspace": "local"}'
```

## Example Result

{% include api/example_result.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath parameters=page.parameters%}

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
