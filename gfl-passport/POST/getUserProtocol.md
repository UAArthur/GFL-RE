# userProtocol

not sure what this is doing

## Request

`POST https://gf-passport.sunborngame.com/passport/userProtocol`

### Headers

| Header          | Value                   |
|-----------------|-------------------------|
| Content-Type    | application/json        |
| User-Agent      | UnityPlayer/2018.4.36f1 |
| X-Unity-Version | 2018.4.36f1             |

### Body

```json
{
  "client_language": "us",
  "lang": "us",
  "channel_id": "Steam",
  "game_channel_id": "en_mica_pc",
  "os": 3
}
```

| Field           | Type   | Description                                 |
|-----------------|--------|---------------------------------------------|
| client_language | string | Client language/region code                 |
| lang            | string | Language code (mirrors client_language?)    |
| channel_id      | string | Platform channel (e.g. `Steam`)             |
| game_channel_id | string | Full channel identifier (e.g. `en_mica_pc`) |
| os              | int    | OS type (`3` = PC?)                         |

## Response

`200 OK` — `application/json`

### Fields

| Field                   | Type   | Description             |
|-------------------------|--------|-------------------------|
| errorReport             | object | Response status wrapper |
| errorReport.protocol_id | int    | Protocol ID             |
| errorReport.error_msg   | string | Error message (Chinese) |
| errorReport.error_no    | int    | Error code              |

### Example Response

```json
{
  "errorReport": {
    "protocol_id": 0,
    "error_msg": "未知错误",
    "error_no": 2
  }
}
```