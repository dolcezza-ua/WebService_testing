# WebService_testing

## Task 1

**Проверить всё ли нормально в работает связка вебсервисов.**

Есть 2 ws :

`WS_1` : http://162.55.220.72:5011/user

`WS_2` : http://23.88.52.139:5012/users_team

- `WS_1` получает запрос от клиента.
  - POST.
  - Body: json
    ```json
    {"user_id": YOUR_ID }
    ```

* После получения запроса `WS_1` отправляет запрос на `WS_2`

  - POST.
  - Body: json

  ```
  {'type': 'padawan', 'spec': 'QA', 'ex': '1', 'current_user': {'uid': YOUR_ID, 'uip:': ‘YOUR_IP’}}
  ```

* `WS_2` принимает запрос от `WS_1`, дополняет полученную Json дополнительной информацией.
* `WS_2` отправляет ответ на `WS_1` в виде
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
* `WS_1` перенаправляет запрос клиенту
