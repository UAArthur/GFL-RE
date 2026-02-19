# heartBeatPacket

Keepalive ping sent periodically to maintain the session.

## Request

```Http
GET http://gf-transit.sunborngame.com/index.php
```

### Headers

| Header          | Value                   |
|-----------------|-------------------------|
| Content-Type    | application/json        |
| User-Agent      | UnityPlayer/2018.4.36f1 |
| X-Unity-Version | 2018.4.36f1             |

### Query Parameters

| Field       | Type              | Description     |
|-------------|-------------------|-----------------|
| c           | `user`            | Category        |
| a           | `heartBeatPacket` | Action          |
| zone_id     | int               | Server/world ID |
| user_id     | int               | Player user ID  |
| update_time | int               | Unix timestamp  |

No request body.

## Response

`200 OK` — `text/html; charset=UTF-8` (JSON body)

### Fields

| Field   | Type   | Description                     |
|---------|--------|---------------------------------|
| 1       | null   | Unknown, always null?           |
| Err_Msg | string | Error message, empty on success |
| Err_No  | int    | Error code, `100` = success     |

### Example Response
```json
{
  "1": null,
  "Err_Msg": "",
  "Err_No": 100
}
```