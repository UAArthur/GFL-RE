# tokenRf

Refresh the session token using a long-lived token.

## Request

`POST https://gf-passport.sunborngame.com/passport/tokenRf`

### Headers

| Header          | Value                   |
|-----------------|-------------------------|
| Content-Type    | application/json        |
| User-Agent      | UnityPlayer/2018.4.36f1 |
| X-Unity-Version | 2018.4.36f1             |
| v               | `3`                     |

### Body

```json
{
  "os": 3,
  "channel_id": "Steam",
  "game_channel_id": "en_mica_pc",
  "lang": "us",
  "client_language": "us",
  "long_token": "<url_encoded_token>"
}
```

| Field           | Type   | Description                                        |
|-----------------|--------|----------------------------------------------------|
| os              | int    | OS type (`3` = PC/Steam?)                          |
| channel_id      | string | Platform channel (e.g. `Steam`)                    |
| game_channel_id | string | Full channel identifier (e.g. `en_mica_pc`)        |
| lang            | string | Language code                                      |
| client_language | string | Client language/region code                        |
| long_token      | string | URL-encoded long-lived token from previous session |

## Response

`200 OK` — `application/json`

### Fields

| Field         | Type   | Description                                              |
|---------------|--------|----------------------------------------------------------|
| token         | string | Short-term token for GameServer authentication           |
| long_token    | string | Long-term token for user identification for /tokenRf     |
| open_id       | int    | User's open ID                                           |
| is_real       | int    | Real-name verified (bool)                                |
| is_guest      | int    | Guest account (bool)                                     |
| is_activation | int    | Account activated (bool)                                 |
| unfreeze_time | int    | Unix timestamp when account unfreezes, `0` if not frozen |
| is_adult      | string | Adult verified (bool as string)                          |
| age           | int    | Unknown                                                  |
| digital_bind  | string | Unknown                                                  |

### Example Response

```json
{
  "token": "<url_encoded_token>",
  "long_token": "<url_encoded_token>",
  "open_id": 8307075,
  "is_real": 0,
  "is_guest": 0,
  "is_activation": 1,
  "unfreeze_time": 0,
  "is_adult": "0",
  "age": -1,
  "digital_bind": "0"
}
```