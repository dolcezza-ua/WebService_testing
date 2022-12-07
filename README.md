# WebService_testing

## Here are three tasks for testing interconnected work of web services <br>(Task 1, Task 2, Task 3).

---

Solution to Task 1 - [Web_Services_1.md](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_1.md); postman collection - [Web_Services_1.postman_collection.json](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_1.postman_collection.json).

Solution to Task 2 - [Web_Services_2.md](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_2.md); postman collection - [Web_Services_2.postman_collection.json](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_2.postman_collection.json).

Solution to Task 3 - [Web_Services_3.md](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_3.md); postman collection - [Web_Services_1.postman_collection.json](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_3.postman_collection.json).

---

## Task 1 (Web_Services_1)

**Verify the interconnected work of web services.**

There are two web services :

`WS_1` - 162.55.220.72:5011

`WS_2` - 23.88.52.139:5012

- `WS_1` receives a request from a client:
  - Method: POST
  - EndPoint: /user
  - Body:

```json
{"user_id": YOUR_ID }
```

- After receiving the request, `WS_1` sends the request to `WS_2`:

  - Method: POST

  * EndPoint: /users_team

  - Body:

```json
{
  "type": "padawan", "spec": "QA", "ex": "1",
  "current_user": {"uid": YOUR_ID, "uip:": YOUR_IP}
}
```

- `WS_2` receives a request from `WS_1`, completes the received response with additional information and sends it all to `WS_1` :

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
    "uid": YOUR_ID,
    "uip:": YOUR_IP
     },
    "ex": "1",
    "spec": "QA",
    "type": "padawan"
    }
}
```

- `WS_1` sends the received response to the client.

### Go to the [Solution of Task 1](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_1.md)

---

## Task 2 (Web_Services_2)

**Verify the interconnected work of web services.**

There are two web services :

`WS_1` - 162.55.220.72:5021

`WS_2` - 23.88.52.139:5022

- `WS_1` receives a request from a client:

  - Method: GET
  - EndPoint: /jobs

  `WS_1` returns to client 'json' response containing 7 vacancies.

- `WS_1` receives a next request from a client:

  - Method: POST
  - EndPoint: /jobs
  - Body:

```json
{ "job_id": JOB_ID }
```

- `WS_1` parses 'json' and sends the request to `WS_2`:

  - Method: POST
  - EndPoint: /get_job
  - Body:

```json
{"job_id": JOB_ID, "j_data": 'json'}
```

- `WS_2` selects 1 vacancy with a key = "job_id" and sends it to `WS_1`. For example, if the key = 6, then the response will be:

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

- `WS_1` sends this received response to the client.

### Go to the [Solution of Task 2](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_2.md)

---

## Task 3 (Web_Services_3)

**Verify the interconnected work of web services.**

There are two web services :

`WS_1` - 162.55.220.72:5031

`WS_2` - 23.88.52.139:5032

- `WS_1` receives a request from a client:

  - Method: GET
  - EndPoint: /jobs_count

* `WS_1` sends the request to `WS_2` :

  - Method: GET
  - EndPoint: /get_jobs_count

* `WS_2` parses 'json' with all vacancies and counts their number. `WS_2` sends a response to WS_1 which will contain:

```json
{ "jobs_count": total_num }
```

- `WS_1` sends this received response to the client.

- `WS_1` receives a next request from a client:

  - Method: GET
  - EndPoint: /all_jobs

  `WS_1` returns to client 'json' response containing all vacancies (7 first vacancies by default + added).

### Adding a job vacancy

- `WS_1` receives a request from a client:

  - Method: POST
  - EndPoint: /add_job
  - Body:

```json
{
  "firm_title": “firm_title”,
  "position_title": “position_title”,
  "skills": [“skill_1”, “skill_2”, “skill_3”]
  "description": description,
  "Job Posting": job_posting,
  "Employee Status": employee_status
}
```

- `WS_1` sends this received request to the `WS_2` to the EndPoint: /add_job_item.

* `WS_2`:

  - parses 'json' with all vacancies and counts their number
  - adds a new vacancy to the general list of vacancies

  * assigns the new vacancy `id = total_num + 1`
  * sends a response to WS_1 which will contain:

```json
{
  "result_message": "Job added. Job id is __",
  "check_message": "call /all_jobs endpoint for checking."
}
```

### Go to the [Solution of Task 3](https://github.com/dolcezza-ua/WebService_testing/blob/main/Web_Services_3.md)
