# bannerAndSpot

Get a list of banners and spots (??) to display on the main menu.

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

| Field | Type            | Description |
|-------|-----------------|-------------|
| c     | `game`          | Category    |
| a     | `bannerAndSpot` | Action      |

No request body.

## Response

`200 OK` — `text/html; charset=UTF-8` (JSON body)

### Fields

| Field   | Type   | Description                     |
|---------|--------|---------------------------------|
| spot    | array  | List of banner/spot entries     |
| Err_Msg | string | Error message, empty on success |
| Err_No  | int    | Error code, `100` = success     |

#### Spot Object

| Field       | Type   | Description                                     |
|-------------|--------|-------------------------------------------------|
| id          | string | Spot ID                                         |
| pic         | string | Image filename                                  |
| type        | string | Spot type (2 = ?, 6 = external link?)           |
| order       | string | Display order                                   |
| delay       | string | Display delay in seconds                        |
| start_time  | string | Visibility start datetime                       |
| end_time    | string | Visibility end datetime                         |
| extra       | string | Extra data — type-dependent (URL or numeric ID) |
| iftimelimit | string | Whether time limit applies (bool)               |
| if_test     | string | Whether this is a test entry (bool)             |

### Example Response

```Json
{
  "spot": [
    {
      "id": "2936",
      "pic": "a46d076e7c64f408_draw_260210110624.jpg",
      "type": "2",
      "order": "14",
      "delay": "3",
      "start_time": "2026-02-17 00:00:00",
      "end_time": "2026-02-24 00:00:00",
      "extra": "4",
      "iftimelimit": "1",
      "if_test": "0"
    },
    {
      "id": "1788",
      "pic": "5450123d7cd8e8ee_draw_230303114317.jpg",
      "type": "6",
      "order": "16",
      "delay": "2",
      "start_time": "2023-03-03 00:00:00",
      "end_time": "2023-03-07 00:00:00",
      "extra": "https://gfus-cdn.sunborngame.com/banner/banben20230303.html",
      "iftimelimit": "0",
      "if_test": "0"
    }
  ],
  "Err_Msg": "",
  "Err_No": 100
}
```