# Student Enrollment Form - Login2XplorE task

A web-based student registration system built using **HTML, CSS, JavaScript**, and **JsonPowerDB** as the backend.  
It enables adding, updating, and managing student data efficiently with fast AJAX interactions.

---

## Table of Contents
- [Description](#description)
- [Benefits of using JsonPowerDB](#benefits-of-using-jsonpowerdb)
- [Scope of functionalities](#scope-of-functionalities)
- [Examples of use](#examples-of-use)
- [Illustrations](#illustrations)
- [Project Status](#project-status)
- [Release History](#release-history)
- [Sources](#sources)
- [Other Information](#other-information)

---

## Description

This Student Enrollment Form allows users to store and manage student information in **JsonPowerDB** using REST APIs and serverless architecture.  
It automatically checks roll numbers and fetches existing data for seamless updating.  
AJAX is used for fast, smooth interactions without reloading the page.  
Supports storage of different data types like numbers, strings, and dates.

---

## Benefits of using JsonPowerDB

- Store structured, semi-structured, and unstructured data, including big-data and files.
- Dynamic relational constraints during CRUD operations without pre-defining PK, FK, or database structures.
- Technology-agnostic: Low-code, easily accessible via HTTP REST APIs.
- Minimal learning curve: Fast development, reduced time to market and costs.
- Developer-friendly database management tools and techniques.

---

## Scope of functionalities

- Add new student records based on roll number.
- Auto-fetch and update existing records.
- Store various data types (numbers, strings, dates).
- Smooth AJAX-powered interactions.
- User-friendly and intuitive interface.
- Fast serverless database operations.

---

## Examples of use

1. **Adding New Student**
   - Fill the form with name, class, DOB, etc., and click *Save*.
2. **Updating Existing Student**
   - Enter the roll number, auto-fetch data, edit details, and click *Update*.

---

## Illustrations

*(You can add screenshots of your form interface here if you want)*

---

## Project Status

✅ **Completed**:  
- All basic functionalities implemented.  
- Fully integrated with JsonPowerDB APIs.  
- Tested for basic CRUD operations.

---

## Release History

- **Version:** 2.0  
- **Released on:** [Github Release Link or Date]  
- **Updates:**  
  - Integrated Execute API function
  - Created dynamic PUT Request function
  - Smooth AJAX-based interactions

### Key API Functions:

```javascript
// Execute API
var baseUrl = "http://api.login2explore.com:5577";
function executeCommand(reqString, apiEndPointUrl) {
    var url = baseUrl + apiEndPointUrl;
    var jsonObj;
    $.post(url, reqString, function (result) {
        jsonObj = JSON.parse(result);
    }).fail(function (result) {
        var dataJsonObj = result.responseText;
        jsonObj = JSON.parse(dataJsonObj);
    });
    return jsonObj;
}

// Create a PUT Request String
function createPUTRequest(connToken, jsonObj, dbName, relName) {
    var putRequest = "{\n"
            + "\"token\" : \"" + connToken + "\","
            + "\"dbName\": \"" + dbName + "\",\n"
            + "\"cmd\" : \"PUT\",\n"
            + "\"rel\" : \"" + relName + "\","
            + "\"jsonStr\": \n" + jsonObj + "\n"
            + "}";
    return putRequest;
}
```

---

## Sources

- [JsonPowerDB Official Documentation](http://login2explore.com/jpdb/docs.html)
- [AJAX jQuery Documentation](https://api.jquery.com/jquery.ajax/)

---

## Other Information

**Tech Stack Used:**
- **Frontend:** HTML, CSS, JavaScript
- **Backend:** JsonPowerDB (via REST API)

---

## Output
- [JsonPowerDB Result](https://drive.google.com/file/d/18Z4MEXJhjiRTynKHgB4rnwK8jel1frtr/view?usp=drive_link)
