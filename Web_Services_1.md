# Solution to Task 1

`WS_1` - 162.55.220.72:5011

`WS_2` - 23.88.52.139:5012

**1.** Request `ws1`

- Protocol: http

- IP: 162.55.220.72

- Port: 5011

- Method: POST

- EndPoint: /user

- request Body raw JSON:

```json
{ "user_id": 5 }
```

**Response:**

```json
{
  "user_divices_data": {
    "comp": {
      "model": "Macbook",
      "monitor_diagonal": 16,
      "ram": 32,
      "resolution": ["Liquid Retina XDR", "3456x2234"],
      "ssd": 1000,
      "year": 2021
    },
    "mobile": {}
  },
  "user_static_data": {
    "current_user": {
      "uid": 5,
      "uip:": "188.167.253.105"
    },
    "ex": "1",
    "spec": "QA",
    "type": "padawan"
  }
}
```

**2.** Request `ws2`

- Protocol: http

- IP: 23.88.52.139

- Port: 5012

- Method: POST

- EndPoint: /users_team

- request Body raw JSON:

```json
{
  "type": "padawan",
  "spec": "QA",
  "ex": "1",
  "current_user": { "uid": 5, "uip:": "188.167.253.105" }
}
```

**Response:**

```json
{
  "current_user": {
    "uid": 5,
    "uip:": "188.167.253.105"
  },
  "ex": "1",
  "spec": "QA",
  "type": "padawan",
  "user_divices_data": {
    "comp": {
      "model": "Macbook",
      "monitor_diagonal": 16,
      "ram": 32,
      "resolution": ["Liquid Retina XDR", "3456x2234"],
      "ssd": 1000,
      "year": 2021
    },
    "mobile": {}
  }
}
```

## Expected Result :

```json
{
  "user_divices_data": {
    "comp": {
      "model": "Macbook",
      "monitor_diagonal": 16,
      "ram": 32,
      "resolution": ["Liquid Retina XDR", "3456x2234"],
      "ssd": 1000,
      "year": 2021
    },
    "mobile": {
      "cpu": "ARM, SnapDragon 840",
      "model": "Samsung a52",
      "os": "Android",
      "ram": 6
    }
  },
  "user_static_data": {
    "current_user": {
      "uid": 1,
      "uip:": "127.0.0.1"
    },
    "ex": "1",
    "spec": "QA",
    "type": "padawan"
  }
}
```

## Conclusion :

Responses contain an empty "mobile" section.

**WS_2 web service does not work correctly.**
