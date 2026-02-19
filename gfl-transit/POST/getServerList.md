# getServerList

Get a list of available servers.

## Request

```http
POST http://gf-transit.sunborngame.com/index.php
```

### Headers

| Header          | Value                             |
|-----------------|-----------------------------------|
| Content-Type    | application/x-www-form-urlencoded |
| User-Agent      | UnityPlayer/2018.4.36f1           |
| X-Unity-Version | 2018.4.36f1                       |

### Body

| Field             | Value           | Description    |
|-------------------|-----------------|----------------|
| c                 | `game`          | Category       |
| a                 | `newserverList` | Action         |
| channel           | `en_mica`       | Region/channel |
| device            | `steam`         | Platform type  |
| platformChannelId | `pc`            | Platform ID    |
| check_version     | `30710`         | Client version |
| rnd               | random int      | Random int??   |

## Response

`200 OK` — `text/html; charset=UTF-8` (XML body)

Returns a list of servers and global config.

### Server fields

| Field        | Type   | Description                   |
|--------------|--------|-------------------------------|
| name         | string | Server name                   |
| addr         | string | Server base URL               |
| worldId      | int    | Server/world ID               |
| recommended  | int    | Whether recommended (bool)    |
| condition    | int    | Unknown                       |
| is_check     | int    | Unknown                       |
| nc           | int    | Unknown                       |
| ab_version   | int    | Asset bundle version          |
| open_time    | int    | Unix timestamp of server open |
| naive_switch | int    | Unknown                       |

### Example Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<servers>
    <server>
        <name>GRIFFIN</name>
        <addr>http://gf-game.sunborngame.com/index.php/1001/</addr>
        <worldId>1001</worldId>
        <recommended>0</recommended>
        <condition>0</condition>
        <is_check>0</is_check>
        <nc>0</nc>
        <ab_version>2026021017</ab_version>
        <open_time>1770174812</open_time>
        <naive_switch>1</naive_switch>
    </server>
    <config>
        <notice_url>http://www.girlsfrontline.co.kr/pages/notice</notice_url>
        <update_log_url>http://www.girlsfrontline.co.kr/pages/update_url</update_log_url>
        <update_start_time>2018-05-16 20:00:43</update_start_time>
        <update_end_time>2036-09-01 00:00:00</update_end_time>
        <client_version>30710</client_version>
        <platform></platform>
        <top_client_version>0</top_client_version>
        <version_desc></version_desc>
    </config>
</servers>
```