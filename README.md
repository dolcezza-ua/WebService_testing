# WebService_testing

## Here are three examples of testing related web services (Task 1, Task 2, Task 3).

The solution to Task 1 is here: [Web_Services_1.md](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_1.md); and postman collection is here: [Web_Services_1.postman_collection.json](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_1.postman_collection.json).

The solution to Task 2 is here: [Web_Services_2.md](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_2.md); and postman collection is here: [Web_Services_2.postman_collection.json](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_2.postman_collection.json).

The solution to Task 3 is here: [Web_Services_3.md](); and postman collection is here: [Web_Services_1.postman_collection.json]().

---

## Task 1 (Web_Services_1)

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

  ```json
  {"type": "padawan", "spec": "QA", "ex": "1", "current_user": {"uid": YOUR_ID, "uip:": YOUR_IP}}
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

---

## Task 2 (Web_Services_2)

**Проверить всё ли нормально в работает связка вебсервисов.**

Есть 2 ws.:

`WS_1` : 162.55.220.72:5021

`WS_2` : 23.88.52.139:5022

- Endpoint /jobs
- 162.55.220.72:5021/jobs
- GET.
  `WS_1` получает запрос от клиента.
  Никаких параметров не нужно
  WS_1 парсит json который храниться на файловой системе сервера. Внутри этого json лежит 7 вакансий.
  WS_1 возвращает клиенту json в котором будет 7 вакансий.
  —-------
- Endpoint /jobs
- 162.55.220.72:5021/jobs
- POST.
  `WS_1` получает запрос от клиента.
  В теле запроса должен быть json

```json
{“job_id”: 1}
```

После получения запроса ws_1 парсит json, в которой 7 вакансий и отправляет запрос на ws_2
23.88.52.139:5022/get_job
В теле запроса должен быть json

```json
{“job_id”: 1, “j_data”: json}
```

WS_2 получает запрос от WS_1
WS_2 выбирает одну вакансию у которой key = “job_id”
WS_2 возвращает json вакансии в WS_1
"6":

```json
{
  "Employee Status": "Full-time",
  "Job Posting": "Nov 15 2022",
  "description": "We are looking for a Quality Assurance (QA) engineer to develop and execute exploratory and automated tests to ensure product quality. QA engineer responsibilities include designing and implementing tests, debugging and defining corrective actions. You will also review system requirements and track quality assurance metrics.",
  "firm_title": "Banyan Data Services",
  "position_title": "Quality Assurance Engineer",
  "skills": ["API Testing", "Mobile testing", "Appium", "Selenium"]
}
```

WS_1 возвращает json вакансии клиенту.

---

## Task 3 (Web_Services_3)

**Проверить всё ли нормально в работает связка вебсервисов.**

Есть 2 ws.
WS_1 - 162.55.220.72:5031
WS_2 - 23.88.52.139:5032
—---------
Endpoint /jobs_count
162.55.220.72:5021/jobs_count
GET.
WS_1 получает запрос от клиента.
Никаких параметров не нужно
WS_1 отправляет запрос на WS_2
23.88.52.139:5032/get_jobs_count

WS_2 получает запрос от WS_1
WS_2 парсит json, в которой 7 вакансий и считает количество вакансий. По умолчанию в json 7 вакансий.
WS_2 отправляет ответ на WS_1 в котором будет json {“jobs_count”:7}
WS_1 получает ответ от WS_2 и отправляет json {“jobs_count”:7} клиенту.
—-----------------------------
Endpoint /all_jobs
162.55.220.72:5021/all_jobs
POST.
WS_1 получает запрос от клиента.
Никаких параметров не нужно
WS_1 отправляет запрос на WS_2Проверить всё ли нормально в работает связка веб сервисов.

Есть 2 ws.
WS_1 - 162.55
23.88.52.139:5032/all_jobs

WS_2 получает запрос от WS_1
WS_2 парсит json, в которой 7 вакансий и считает количество вакансий. По умолчанию в json 7 вакансий.
WS_2 отправляет ответ на WS_1 в котором будет json + все добавленные пользователем вакансии.
WS_1 получает ответ от WS_2 и отправляет json клиенту.
—-----------------------------

Endpoint /add_job
162.55.220.72:5021/add_job
POST.
WS_1 получает запрос от клиента.
Никаких параметров не нужно
WS_1 отправляет запрос на WS_2
23.88.52.139:5032/add_job_item
В теле запроса должен быть json
{"firm_title": “firm_title”,
"position_title": “position_title”,
"skills": [“skill_1”, “skill_2”, “skill_3”]
"description": description,
"Job Posting": job_posting,
"Employee Status": employee_status}

WS_2 получает запрос от WS_1
WS_2 парсит json, в которой 7 вакансий и считает количество вакансий. По умолчанию в json 7 вакансий.
WS_2 добавляет в json присланную из WS_1 json.
У добавленной вакансии будет id = +1 к общему количеству вакансий в json (n+1)

WS_2 отправляет ответ на WS_1 в котором будет json
{"result_message":"Job added. Job id is 8",
"check_message": "call /all_jobs endpoint for checking."}
