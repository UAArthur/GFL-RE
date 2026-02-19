# login

openId login endpoint. Requests a token for the GameServer.

## Request

`POST https://gf-passport.sunborngame.com/passport/login`

### Headers

| Header          | Value                   |
|-----------------|-------------------------|
| Content-Type    | application/json        |
| User-Agent      | UnityPlayer/2018.4.36f1 |
| X-Unity-Version | 2018.4.36f1             |

### Body

```json
{
  "os": 3,
  "channel_id": "Steam",
  "account": "example@test.com",
  "game_channel_id": "en_mica_pc",
  "lang": "us",
  "type": "0",
  "passwd": "<md5_hash_of_password>",
  "client_language": "us"
}
```

| Field           | Type   | Description                                 |
|-----------------|--------|---------------------------------------------|
| os              | int    | OS type (`3` = PC?)                         |
| channel_id      | string | Platform channel (e.g. `Steam`)             |
| account         | string | User account (e.g. email)                   |
| game_channel_id | string | Full channel identifier (e.g. `en_mica_pc`) |
| lang            | string | Language code (mirrors client_language?)    |
| type            | string | Login type (e.g. `0` for email?)            |
| passwd          | string | Password hash (MD5 of password?)            |
| client_language | string | Client language/region code                 |

## Response

`200 OK` — `application/json`

### Fields

| Field         | Type   | Description                                          |
|---------------|--------|------------------------------------------------------|
| token         | string | Short-term token for GameServer authentication       |
| long_token    | string | Long-term token for user identification for /tokenRf |
| open_id       | int    | User's open ID                                       |
| delete_status | int    | Account deletion status (ig)                         |
| cancel_token  | string | (not sure what this is)                              |
| delete_time   | int    | Timestamp of account deletion (ig?)                  |

### Example Response

```json
{
  "token": "<url_encoded_token>",
  "long_token": "<url_encoded_token>",
  "open_id": 9296221,
  "delete_status": 0,
  "cancel_token": "",
  "delete_time": 0
}
```