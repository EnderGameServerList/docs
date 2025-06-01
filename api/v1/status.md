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

# Status

Abrufen von Statusdaten zu einem Game Server über einen bestimmten Zeitraum.

## Endpoint

`GET /v1/server/{game_type}/{name}/status/{time_span}`

### Parameters

- `game_type` *(Pfad, erforderlich)* – Enum: `minecraft_java`, `minecraft_bedrock`
- `name` *(Pfad, erforderlich)* – Der interne Servername (String)
- `time_span` *(Pfad, erforderlich)* – Enum: `12h`, `24h`, `48h`

### Responses

- **200 OK** – Successful Response:

  ```json
  {
    "server_info": {
      "name": "string",
      "display_name": "string",
      "type": "string",
      "ip": "string",
      "port": 0,
      "mods": []
    },
    "status": {}
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
