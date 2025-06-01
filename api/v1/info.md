---
date: 2025-06-01
category: [API]
tags: [APIv1]
description: API - Info

author:
  - name: Endkind
    link: https://github.com/Endkind
    avatar: https://github.com/Endkind.png
---

# Info

Abrufen von allgemeinen Informationen zu einem bestimmten Game Server.

## Endpoint

`GET /v1/server/{game_type}/{name}/info`

### Parameters

- `game_type` *(Pfad, erforderlich)* – Enum: `minecraft_java`, `minecraft_bedrock`
- `name` *(Pfad, erforderlich)* – Der interne Servername (String)

### Responses

- **200 OK** – Successful Response:

  ```json
  {
    "name": "string",
    "display_name": "string",
    "type": "string",
    "ip": "string",
    "port": 0,
    "mods": []
  }
  ```

- **404 Not Found** – Game Server Not found

- **422 Validation Error** – Validation Error:

  ```json
  {
    "detail": [
      {
        "loc": [
          "string",
          0
        ],
        "msg": "string",
        "type": "string"
      }
    ]
  }
  ```
