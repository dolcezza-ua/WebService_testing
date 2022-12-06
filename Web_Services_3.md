# Solution to Task 3

`WS_1` - 162.55.220.72:5031

`WS_2` - 23.88.52.139:5032

**1.** Request `ws1(3)` to the WS_1

- Protocol: http

- IP: 162.55.220.72

- Port: 5031

- Method: GET

- EndPoint: /jobs_count

**Response:**

```json
{
  "jobs_count": 99
}
```

**2.** Request `ws2(3)` to the WS_2

- Protocol: http

- IP: 23.88.52.139

- Port: 5032

- Method: GET

- EndPoint: /get_jobs_count

**Response:**

```json
{
  "jobs_count": 99
}
```

**3.** Request `ws3(3)` to the WS_1

- Protocol: http

- IP: 162.55.220.72

- Port: 5031

- Method: GET

- EndPoint: /all_jobs

**Response** [^json]

**4.** Request `ws4(3)` to the WS_1

- Protocol: http

- IP: 162.55.220.72

- Port: 5031

- Method: POST

- EndPoint: /add_job

- request Body raw JSON:

  ```json
  {
    "firm_title": "GlobalLogic",
    "position_title": "QA Engineer",
    "skills": ["JavaScript", "Python", "Postman"],
    "description": "Test plan development. Working from the specifications to develop and perform test plans that ensure the accurate functioning of the system. Issue management.Identifying, raising & prioritizing issues and tracking these to a successful resolution. Drive defect management and RCA for various client projects and find opportunities for improvement.",
    "Job Posting": "Nov 20 2022",
    "Employee Status": "full-time"
  }
  ```

  **Response:**

```json
{
  "check_message": "call /all_jobs endpoint for checking.",
  "result_essage": "Job added. Job id is 100"
}
```

**5.** Request `ws5(3)` to the WS_2

- Protocol: http

- IP: 23.88.52.139

- Port: 5032

- Method: POST

- EndPoint: /add_job_item

- request Body raw JSON:

```json
{
  "firm_title": "SoftServe",
  "position_title": "Junior Tester",
  "skills": ["JavaScript", "Python", "Jenkins"],
  "description": "Building, maintaining and contributing to the development of industry recognised standard testing methodologies, and processes. Producing clear specification documents, designing and implementing Automated UW Rules, building and carrying out unit and scenario tests. Working through timelines and within defined processes. To analyse data and underwriting outcomes to improve rule performance will compliment your core responsibilities.",
  "Job Posting": "Nov 20 2022",
  "Employee Status": "full-time"
}
```

**Response:**

```json
{
  "check_message": "call /all_jobs endpoint for checking.",
  "result_essage": "Job added. Job id is 101"
}
```

## Conclusion :

- The Response to the Request ws3(3) contains an empty "Job Posting" section, except for items 1-7(which contain default information). Therefore, an error occurs when adding each new job position.
- **This means that the `WS_2` web service does not work correctly and does not give correct response(when sending a request to it, using the POST method, to the EndPoint "add_job_item" ).**

---

---

[^json]:

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
  "10": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Acosoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Janjins", "QA Automation"]
  },
  "100": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Test plan development. Working from the specifications to develop and perform test plans that ensure the accurate functioning of the system. Issue management.Identifying, raising & prioritizing issues and tracking these to a successful resolution. Drive defect management and RCA for various client projects and find opportunities for improvement.",
    "firm_title": "GlobalLogic",
    "position_title": "QA Engineer",
    "skills": ["JavaScript", "Python", "Postman"]
  },
  "101": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Building, maintaining and contributing to the development of industry recognised standard testing methodologies, and processes. Producing clear specification documents, designing and implementing Automated UW Rules, building and carrying out unit and scenario tests. Working through timelines and within defined processes. To analyse data and underwriting outcomes to improve rule performance will compliment your core responsibilities.",
    "firm_title": "SoftServe",
    "position_title": "Junior Tester",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "102": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Great possibility",
    "firm_title": "Samsung",
    "position_title": "QA lead engineer",
    "skills": [
      "Problem_solving_abilities",
      "Team leading abilities",
      "Collaboration_talent",
      "API Testing",
      "Mobile testing",
      "Selenium"
    ]
  },
  "11": {
    "Employee Status": "Part-time",
    "Job Posting": " ",
    "description": "Nice Job",
    "firm_title": "MegaSoft",
    "position_title": "Junior QA Engineer",
    "skills": ["JS", "Postman", "Functional QA", "soft skills"]
  },
  "12": {
    "Employee Status": "Part-time",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "ITX",
    "position_title": "Junior QA",
    "skills": ["postman", "js", "client_server", "api_testing", "soft skills"]
  },
  "13": {
    "Employee Status": "part-time",
    "Job Posting": " ",
    "description": "Nice Job",
    "firm_title": "MegaSoft",
    "position_title": "Junior QA",
    "skills": ["JS", "Postman", "Functional QA ", "soft skills"]
  },
  "14": {
    "Employee Status": "Part-time",
    "Job Posting": " ",
    "description": "Nice Job",
    "firm_title": "MegaSoft",
    "position_title": "Junior QA Engineer",
    "skills": ["JS", "Postman", "Functional QA", "Soft skills"]
  },
  "15": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "AcoSoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Jenkins", "QA Automation"]
  },
  "16": {
    "Employee Status": "all-time",
    "Job Posting": " ",
    "description": "Never Sleep Job",
    "firm_title": "ITX",
    "position_title": "POMOGATOR",
    "skills": ["Any_time", "Help_to_menthors", "Glory to Ukraine"]
  },
  "17": {
    "Employee Status": "Employee_statuS",
    "Job Posting": " ",
    "description": "DescriptioN",
    "firm_title": "Qwerty",
    "position_title": "QA_Eng",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "18": {
    "Employee Status": "employee_status",
    "Job Posting": " ",
    "description": "description",
    "firm_title": "firm_title",
    "position_title": "position_title",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "19": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Level 100",
    "firm_title": "QA_Company",
    "position_title": "QA Engineer",
    "skills": ["Postman", "JS", "HTML"]
  },
  "2": {
    "Employee Status": "Full-time",
    "Job Posting": "Nov 10 2022",
    "description": "Under supervision, to monitor and evaluate testing results against predetermined objectives and apply recommended actions for improvements; to perform the design, development, execution and reporting efforts for projects using a single software testing technology competency (i.e., functional, systems, automation, performance, data accuracy, etc.) within a Waterfall and/or Agile software development process.",
    "firm_title": "The County of Santa Clara - Assessor",
    "position_title": "Test Engineer",
    "skills": ["DBAs", "Load test", "test plans"]
  },
  "20": {
    "Employee Status": "employee_status",
    "Job Posting": " ",
    "description": "description",
    "firm_title": "firm_title",
    "position_title": "position_title",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "21": {
    "Employee Status": "all-time",
    "Job Posting": " ",
    "description": "Never Sleep Job",
    "firm_title": "ITX",
    "position_title": "POMOGATOR",
    "skills": ["Any_time", "Help_to_menthors", "Glory to Ukraine"]
  },
  "22": {
    "Employee Status": "employee_status",
    "Job Posting": " ",
    "description": "description",
    "firm_title": "firm_title",
    "position_title": "position_title",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "23": {
    "Employee Status": "Full_stuck",
    "Job Posting": " ",
    "description": "Under supervision",
    "firm_title": "Luntik_TM",
    "position_title": "Fiksik",
    "skills": ["Repear", "Worker"]
  },
  "24": {
    "Employee Status": "Full_stuck",
    "Job Posting": " ",
    "description": "Under supervision",
    "firm_title": "Luntik_TM",
    "position_title": "Fiksik",
    "skills": ["Repear", "Worker"]
  },
  "25": {
    "Employee Status": "Full_stuck",
    "Job Posting": " ",
    "description": "Under supervision",
    "firm_title": "Luntik_TM",
    "position_title": "Fiksik",
    "skills": ["Repear", "Worker"]
  },
  "26": {
    "Employee Status": "alllll time",
    "Job Posting": " ",
    "description": "fake job",
    "firm_title": "Broken dreams",
    "position_title": "QA_automation_QA",
    "skills": ["Java", "Jenkins", "QA Automation"]
  },
  "27": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Be like a senior",
    "firm_title": "Sumsung",
    "position_title": "Junior QA",
    "skills": ["Postman", "Sql", "JS"]
  },
  "28": {
    "Employee Status": "Part-time",
    "Job Posting": " ",
    "description": "Nice Job",
    "firm_title": "MegaSoft",
    "position_title": "Junior QA Engineer",
    "skills": ["JS", "Postman", "Functional QA", "soft skills"]
  },
  "29": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Experience with Functional Testing, including Regression Testing, Integration Testing, and API Testing. Experience with creating and executing test scripts. Experience testing developments against wireframes and style guide. Experience with systems, integration, and user acceptance testing. Experience in working with offshore /onsite Model",
    "firm_title": "Cognizant Technology Solutions",
    "position_title": "QA Functional Tester",
    "skills": ["postman", "js", "client_server", "api_testing"]
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
  "30": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "As a Electronics Engineer Testing your participation in the planning and creation of test plans and test instructions based on customer requirements to ensure development quality.",
    "firm_title": "Brunel GmbH",
    "position_title": "Electronics Engineer Testing",
    "skills": ["C/C++", "LabView", "client_server", "api_testing"]
  },
  "31": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "As a Electronics Engineer Testing your participation in the planning and creation of test plans and test instructions based on customer requirements to ensure development quality.",
    "firm_title": "Brunel GmbH",
    "position_title": "Electronics Engineer Testing",
    "skills": ["C/C++", "LabView", "client_server", "api_testing"]
  },
  "32": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "33": {
    "Employee Status": "Part-time",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "MegaSoft",
    "position_title": "Junior QA Engineer",
    "skills": ["postman", "js", "soft skills", "functional QA"]
  },
  "34": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Experience with systems, integration, and user acceptance testing.",
    "firm_title": "Pluh inc",
    "position_title": "QA automation",
    "skills": ["postman", "js", "client_server"]
  },
  "35": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Experience with systems, integration, and user acceptance testing.",
    "firm_title": "Pluh inc",
    "position_title": "QA automation",
    "skills": ["postman", "js", "client_server"]
  },
  "36": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Experience with systems, integration, and user acceptance testing.",
    "firm_title": "Pluh inc",
    "position_title": "QA automation",
    "skills": ["postman", "js", "client_server"]
  },
  "37": {
    "Employee Status": "part-time",
    "Job Posting": " ",
    "description": "We are seeking a System Integration and Test Engineer to be responsible for development and maintenance of test scripts to be used during all satellite test phases. You should understand principles and disciplines such as policy, procedures, process discipline, operations, safety, and command media to perform job duties of Space Vehicle Test Engineering.",
    "firm_title": "LOCKHEED MARTIN CORPORATION",
    "position_title": "Test Engineer",
    "skills": ["game to dota 2"]
  },
  "38": {
    "Employee Status": "Part-time",
    "Job Posting": " ",
    "description": "Focusing on web automation",
    "firm_title": "Jade Global",
    "position_title": "Senior QA",
    "skills": ["Postman", "Java", "Jmeter"]
  },
  "39": {
    "Employee Status": "Part-time",
    "Job Posting": " ",
    "description": "Focusing on web automation",
    "firm_title": "Jade Global",
    "position_title": "Senior QA",
    "skills": ["Postman", "Java", "Jmeter"]
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
  "40": {
    "Employee Status": "no more than 20 minutes",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "Engineering company",
    "position_title": "Big Boss",
    "skills": ["I know how to yell", "I do not want to work"]
  },
  "41": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "DEV",
    "firm_title": "Jade Global",
    "position_title": "Junior Dev",
    "skills": ["Python", "Java", "C++"]
  },
  "42": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "43": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "44": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "45": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "46": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "47": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "48": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "49": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
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
  "50": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "51": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "52": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "53": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "54": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "55": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "56": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "57": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "58": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "59": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "6": {
    "Employee Status": "Full-time",
    "Job Posting": "Nov 15 2022",
    "description": "We are looking for a Quality Assurance (QA) engineer to develop and execute exploratory and automated tests to ensure product quality. QA engineer responsibilities include designing and implementing tests, debugging and defining corrective actions. You will also review system requirements and track quality assurance metrics.",
    "firm_title": "Banyan Data Services",
    "position_title": "Quality Assurance Engineer",
    "skills": ["API Testing", "Mobile testing", "Appium", "Selenium"]
  },
  "60": {
    "Employee Status": "full time",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "Horns and hooves",
    "position_title": "sit chair",
    "skills": ["anwser the questions"]
  },
  "61": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Working closely with the business functions such as Quality and Regulatory Affairs to create ongoing enhancements and capabilities. Participating in deployment projects as a QA – including but not limited to requirements analysis, requirements documentation, and the creation and execution of test scripts.",
    "firm_title": "Jade Global",
    "position_title": "Jr. QA",
    "skills": [
      "functional testing",
      "user acceptance testing",
      "requirements documentation testing"
    ]
  },
  "62": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "63": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "64": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "65": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "66": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "67": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "Google",
    "position_title": "QA Manual",
    "skills": ["JS", "Python", "QA Automatoin"]
  },
  "68": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "69": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "7": {
    "Employee Status": " Full-time",
    "Job Posting": "Nov 29 2022",
    "description": "Focusing on web automation the team is primarily looking for people who experience in UI and API testing. Will need to have experience with Postman, Java, Selenium, TestNG and Cucumber. Develop, modify, automate and execute automated test scripts for various business scenarios in collaboration with Developers, Tech Leads and product partners. Keep up with close to 100% automation coverage for the teams. Improve areas where there are gap in automation coverage.",
    "firm_title": "Tek Ninjas",
    "position_title": "QA Engineer",
    "skills": ["Java"]
  },
  "70": {
    "Employee Status": "employee_status",
    "Job Posting": " ",
    "description": "description",
    "firm_title": "firm_title",
    "position_title": "position_title",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "71": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "AMAZON",
    "position_title": "Project Manager",
    "skills": ["Team management", "Time management", "Critical thinking"]
  },
  "72": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "73": {
    "Employee Status": "Full_time",
    "Job Posting": " ",
    "description": "I'm Iron Man",
    "firm_title": "StarkIndustries",
    "position_title": "Iron_Man",
    "skills": ["Genius", "PlayBoy", "Billionaire", "Philanthropist"]
  },
  "74": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "75": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "UASoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Postman", "SQL"]
  },
  "76": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "UASoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Postman", "SQL"]
  },
  "77": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "78": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "UASoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Postman", "SQL"]
  },
  "79": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "8": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "AcoSoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Jenkins", "QA Automation"]
  },
  "80": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "81": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "82": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "A real opportunity to go ahead",
    "firm_title": "UASoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Postman", "SQL"]
  },
  "83": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "Google",
    "position_title": "QA Manual",
    "skills": ["JS", "Python", "QA Automatoin"]
  },
  "84": {
    "Employee Status": "part-time",
    "Job Posting": " ",
    "description": "Nice Job",
    "firm_title": "Allsafe",
    "position_title": "AQA Engineer",
    "skills": ["Python", "Selenium", "QA Automation"]
  },
  "85": {
    "Employee Status": "part-time",
    "Job Posting": " ",
    "description": "Nice Job",
    "firm_title": "Allsafe",
    "position_title": "AQA Engineer",
    "skills": ["Python", "Selenium", "QA Automation"]
  },
  "86": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "rukovodsvo paradom",
    "firm_title": "Roga and Kopita",
    "position_title": "velikiy kombinator",
    "skills": [
      "problem_solving_abilities",
      "communication",
      "collaboration_talent"
    ]
  },
  "87": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "Google",
    "position_title": "QA Manual",
    "skills": ["JS", "Python", "QA Automatoin"]
  },
  "88": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "89": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "9": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "AcoSoft",
    "position_title": "QA Engineer",
    "skills": ["Java", "Jenkins", "QA Automation"]
  },
  "90": {
    "Employee Status": "full-time",
    "Job Posting": " ",
    "description": "Good Job",
    "firm_title": "Lenovo",
    "position_title": "AQA Engineer",
    "skills": ["JavaScript", "Python", "Jenkins"]
  },
  "91": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "92": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "description_something",
    "firm_title": "Name_1",
    "position_title": "Position_1",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "93": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Be like a senior",
    "firm_title": "Forex",
    "position_title": "Junior QA",
    "skills": ["Postman", "Sql", "JS"]
  },
  "94": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "rukovodsvo paradom",
    "firm_title": "Roga and Kopita",
    "position_title": "velikiy kombinator",
    "skills": [
      "problem_solving_abilities",
      "communication",
      "collaboration_talent"
    ]
  },
  "95": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Nice job",
    "firm_title": "Google",
    "position_title": "QA Manual",
    "skills": ["JS", "Python", "QA Automatoin"]
  },
  "96": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "Experience with Functional Testing, including Regression Testing, Integration Testing, and API Testing. Experience with creating and executing test scripts. Experience testing developments against wireframes and style guide. Experience with systems, integration, and user acceptance testing. Experience in working with offshore /onsite Model",
    "firm_title": "Cognizant Technology Solutions",
    "position_title": "Middle QA  tester",
    "skills": ["postman", "python", "client_server", "api_testing"]
  },
  "97": {
    "Employee Status": "employee_status",
    "Job Posting": " ",
    "description": "description",
    "firm_title": "firm_title",
    "position_title": "position_title",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "98": {
    "Employee Status": "employee_status",
    "Job Posting": " ",
    "description": "description",
    "firm_title": "firm_title",
    "position_title": "position_title",
    "skills": ["skill_1", "skill_2", "skill_3"]
  },
  "99": {
    "Employee Status": "Full-time",
    "Job Posting": " ",
    "description": "rukovodsvo paradom",
    "firm_title": "Roga and Kopita",
    "position_title": "velikiy kombinator",
    "skills": [
      "problem_solving_abilities",
      "communication",
      "collaboration_talent"
    ]
  }
}
```
