---
method: post
parameters: true
endpoint: assets.setAsset
authentication: true
category: assets
permalink: /developer-guides/rest-api/assets/setasset/
--- 

{% capture fullPath %}{{ "/api/v1/" | append: page.endpoint }}{% endcapture %}

# Set Asset

{% include api/specific_endpoint.html category=page.category endpoint=page.endpoint method=page.method authentication=page.authentication fullPath=fullPath %}
<!-- 
Set an asset by name. Requires `manage-assets` permission.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/assets.setAsset` | `yes` | `POST` |
 -->
## Payload

{% include api/list_parameters.html category=page.category endpoint=page.endpoint method=page.method fullPath=fullPath %}
<!-- 
| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `assetName` | mylogo.png | Required | Asset File to upload. |
| `refreshAllClients` | `true` | Optional | If needs refresh all clients to apply changes immediately. | -->

`assetName` can be one of these: [`logo`, `background`, `favicon_ico`, `favicon`, `favicon_16`, `favicon_32`, `favicon_192`, `favicon_512`, `touchicon_180`,
`touchicon_180_pre`, `tile_70`, `tile_144`, `tile_150`, `tile_310_square`, `tile_310_wide`, `safari_pinned ]`

## Upload a file

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -F "logo=@mylogo.png" \
     http://localhost:3000/api/v1/assets.setAsset
```

### Example Result

```json
{
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.69.0 | Added |
