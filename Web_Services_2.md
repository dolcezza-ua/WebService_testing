`WS_1` : 162.55.220.72:5021

`WS_2` : 23.88.52.139:5022

**1.** Request `ws1(2)`

- Protocol: http

- IP: 162.55.220.72

- Port: 5021

- Method: GET

- EndPoint: /jobs

**Response:**

```json
{
  "1": {
    "Employee Status": "Full-time",
    "Job Posting": "Aug 02 2022",
    "description": "Experience with Functional Testing, including Regression Testing, Integration Testing, and API Testing. Experience with creating and executing test scripts. Experience testing developments against wireframes and style guide. Experience with systems, integration, and user acceptance testing. Experience in working with offshore /onsite Model",
    "firm_title": "Cognizant Technology Solutions",
    "position_title": "QA Functional Tester",
    "skills": ["postman", "js", "client_server", "api_testing"]
  },
  "2": {
    "Employee Status": "Full-time",
    "Job Posting": "Nov 10 2022",
    "description": "Under supervision, to monitor and evaluate testing results against predetermined objectives and apply recommended actions for improvements; to perform the design, development, execution and reporting efforts for projects using a single software testing technology competency (i.e., functional, systems, automation, performance, data accuracy, etc.) within a Waterfall and/or Agile software development process.",
    "firm_title": "The County of Santa Clara - Assessor",
    "position_title": "Test Engineer",
    "skills": ["DBAs", "Load test", "test plans"]
  },
  "3": {
    "Employee Status": "Full-time",
    "Job Posting": "Nov 30 2022",
    "description": "Working closely with the business functions such as Quality and Regulatory Affairs to create ongoing enhancements and capabilities. Participating in deployment projects as a QA – including but not limited to requirements analysis, requirements documentation, and the creation and execution of test scripts.",
    "firm_title": "Jade Global",
    "position_title": "Jr. QA",
    "skills": [
      "functional testing",
      "user acceptance testing",
      "requirements documentation testing"
    ]
  },
  "4": {
    "Employee Status": "Full-time",
    "Job Posting": "Nov 22 2022",
    "description": "We are seeking a System Integration and Test Engineer to be responsible for development and maintenance of test scripts to be used during all satellite test phases. You should understand principles and disciplines such as policy, procedures, process discipline, operations, safety, and command media to perform job duties of Space Vehicle Test Engineering.",
    "firm_title": "LOCKHEED MARTIN CORPORATION",
    "position_title": "Test Engineer",
    "skills": [
      "Python Scripting Experience",
      "functionality test",
      "verbal communication skills",
      " strong social skills",
      "Familiarity with Git"
    ]
  },
  "5": {
    "Employee Status": "Full-time",
    "Job Posting": "Oct 14, 2022",
    "description": "The Bluetooth Quality team is looking for a motivated, highly-technical Bluetooth Quality Engineer with an ability to seek solutions to unusual problems with valued interpersonal skills. You will be responsible for ensuring the best customer experience and quality of Bluetooth in the latest Apple products.",
    "firm_title": "Apple",
    "position_title": "Wireless Bluetooth QA Engineer",
    "skills": [
      "Excellent written and verbal skills",
      "Excellent teammate ",
      "Bluetooth testing"
    ]
  },
  "6": {
    "Employee Status": "Full-time",
    "Job Posting": "Nov 15 2022",
    "description": "We are looking for a Quality Assurance (QA) engineer to develop and execute exploratory and automated tests to ensure product quality. QA engineer responsibilities include designing and implementing tests, debugging and defining corrective actions. You will also review system requirements and track quality assurance metrics.",
    "firm_title": "Banyan Data Services",
    "position_title": "Quality Assurance Engineer",
    "skills": ["API Testing", "Mobile testing", "Appium", "Selenium"]
  },
  "7": {
    "Employee Status": " Full-time",
    "Job Posting": "Nov 29 2022",
    "description": "Focusing on web automation the team is primarily looking for people who experience in UI and API testing. Will need to have experience with Postman, Java, Selenium, TestNG and Cucumber. Develop, modify, automate and execute automated test scripts for various business scenarios in collaboration with Developers, Tech Leads and product partners. Keep up with close to 100% automation coverage for the teams. Improve areas where there are gap in automation coverage.",
    "firm_title": "Tek Ninjas",
    "position_title": "QA Engineer",
    "skills": ["Java"]
  }
}
```

**2.** Request `ws2(2)`

- Protocol: http

- IP: 162.55.220.72

- Port: 5021

- Method: POST

- EndPoint: /jobs

- request Body raw JSON:

  ```json
  { "job_id": 6 }
  ```

**Response:**

```json
{
  "Employee Status": "Full-time",
  "description": "We are looking for a Quality Assurance (QA) engineer to develop and execute exploratory and automated tests to ensure product quality. QA engineer responsibilities include designing and implementing tests, debugging and defining corrective actions. You will also review system requirements and track quality assurance metrics.",
  "firm_title": "Banyan Data Services",
  "position_title": "Quality Assurance Engineer",
  "skills": ["API Testing", "Mobile testing", "Appium", "Selenium"]
}
```

**3.** Request `ws3(2)`

- Protocol: http

- IP: 23.88.52.139

- Port: 5022

- Method: POST

- EndPoint: /get_job

- request Body raw JSON:

```json
{
  "job_id": 6,
  "j_data": {
    "1": {
      "Employee Status": "Full-time",
      "Job Posting": "Aug 02 2022",
      "description": "Experience with Functional Testing, including Regression Testing, Integration Testing, and API Testing. Experience with creating and executing test scripts. Experience testing developments against wireframes and style guide. Experience with systems, integration, and user acceptance testing. Experience in working with offshore /onsite Model",
      "firm_title": "Cognizant Technology Solutions",
      "position_title": "QA Functional Tester",
      "skills": ["postman", "js", "client_server", "api_testing"]
    },
    "2": {
      "Employee Status": "Full-time",
      "Job Posting": "Nov 10 2022",
      "description": "Under supervision, to monitor and evaluate testing results against predetermined objectives and apply recommended actions for improvements; to perform the design, development, execution and reporting efforts for projects using a single software testing technology competency (i.e., functional, systems, automation, performance, data accuracy, etc.) within a Waterfall and/or Agile software development process.",
      "firm_title": "The County of Santa Clara - Assessor",
      "position_title": "Test Engineer",
      "skills": ["DBAs", "Load test", "test plans"]
    },
    "3": {
      "Employee Status": "Full-time",
      "Job Posting": "Nov 30 2022",
      "description": "Working closely with the business functions such as Quality and Regulatory Affairs to create ongoing enhancements and capabilities. Participating in deployment projects as a QA – including but not limited to requirements analysis, requirements documentation, and the creation and execution of test scripts.",
      "firm_title": "Jade Global",
      "position_title": "Jr. QA",
      "skills": [
        "functional testing",
        "user acceptance testing",
        "requirements documentation testing"
      ]
    },
    "4": {
      "Employee Status": "Full-time",
      "Job Posting": "Nov 22 2022",
      "description": "We are seeking a System Integration and Test Engineer to be responsible for development and maintenance of test scripts to be used during all satellite test phases. You should understand principles and disciplines such as policy, procedures, process discipline, operations, safety, and command media to perform job duties of Space Vehicle Test Engineering.",
      "firm_title": "LOCKHEED MARTIN CORPORATION",
      "position_title": "Test Engineer",
      "skills": [
        "Python Scripting Experience",
        "functionality test",
        "verbal communication skills",
        " strong social skills",
        "Familiarity with Git"
      ]
    },
    "5": {
      "Employee Status": "Full-time",
      "Job Posting": "Oct 14, 2022",
      "description": "The Bluetooth Quality team is looking for a motivated, highly-technical Bluetooth Quality Engineer with an ability to seek solutions to unusual problems with valued interpersonal skills. You will be responsible for ensuring the best customer experience and quality of Bluetooth in the latest Apple products.",
      "firm_title": "Apple",
      "position_title": "Wireless Bluetooth QA Engineer",
      "skills": [
        "Excellent written and verbal skills",
        "Excellent teammate ",
        "Bluetooth testing"
      ]
    },
    "6": {
      "Employee Status": "Full-time",
      "Job Posting": "Nov 15 2022",
      "description": "We are looking for a Quality Assurance (QA) engineer to develop and execute exploratory and automated tests to ensure product quality. QA engineer responsibilities include designing and implementing tests, debugging and defining corrective actions. You will also review system requirements and track quality assurance metrics.",
      "firm_title": "Banyan Data Services",
      "position_title": "Quality Assurance Engineer",
      "skills": ["API Testing", "Mobile testing", "Appium", "Selenium"]
    },
    "7": {
      "Employee Status": " Full-time",
      "Job Posting": "Nov 29 2022",
      "description": "Focusing on web automation the team is primarily looking for people who experience in UI and API testing. Will need to have experience with Postman, Java, Selenium, TestNG and Cucumber. Develop, modify, automate and execute automated test scripts for various business scenarios in collaboration with Developers, Tech Leads and product partners. Keep up with close to 100% automation coverage for the teams. Improve areas where there are gap in automation coverage.",
      "firm_title": "Tek Ninjas",
      "position_title": "QA Engineer",
      "skills": ["Java"]
    }
  }
}
```

**Response:**

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

## Expected Result :

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

## Conclusion :

There is no "Job Posting" section in Request ws2(2).

**WS_1 web service does not work correctly (when sending a request to the EndPoint "jobs" using the POST method).**
