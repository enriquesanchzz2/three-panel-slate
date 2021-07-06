# Health Checks
The Health Checks resource enables you to interact with the Health Check Forms files of a Test Case. The following table describes the available endpoints of the Health Checks resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-health-checks-projects-project-testcases-testcase-config" class="get-endpoint-word">GET</a>  /health-checks/projects/{project}/testcases/{testcase}/config | Retrieves the Health Checks confifgurations of a Test Case. |
| <a href="#put-health-checks-projects-project-testcases-testcase-config" class="put-endpoint-word">PUT</a>   /health-checks/projects/{project}/testcases/{testcase}/config | Updates the Health Checks confifguration of a Test Case. |

## GET /HEALTH-CHECKS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG
<p class="get-endpoint">GET</p> 

### Summary
The **GET /HEALTH-CHECKS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG** endpoint retrieves the Health Checks confifgurations of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/health-checks/projects/{project}/testcases/{testcase}/config'
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case| Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/health-checks/projects/seed-project/testcases/get-an-url/config'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/health-checks/projects/seed-project/testcases/get-an-url/config` 

### Sample Response Body
```json
[
  {
    "checkName": "SUCC VS FAILED",
    "badResultInput": {
      "name": "badResult",
      "type": "number",
      "defaultValue": 50,
      "placeholder": "The proportion of failing requests",
      "required": false,
      "format": "%",
      "allowDecimals": false,
      "max": 100,
      "min": 5
    },
    "badResult": 50,
    "badIncrementInput": {
      "name": "badIncrement",
      "type": "number",
      "placeholder": "The proportion of failing requests",
      "required": false,
      "format": "%",
      "allowDecimals": false,
      "max": 100,
      "min": 5
    },
    "isToggleOn": true
  },
  {
    "checkName": "AVG RESPONSE TIME",
    "badResultInput": {
      "name": "badResult",
      "type": "number",
      "defaultValue": 800,
      "placeholder": "The average response time",
      "required": false,
      "format": "ms",
      "allowDecimals": false,
      "min": 100
    },
    "badResult": 800,
    "badIncrementInput": {
      "name": "badIncrement",
      "type": "number",
      "placeholder": "The average response time",
      "required": false,
      "format": "times",
      "allowDecimals": true,
      "min": 1.05
    },
    "isToggleOn": true
  },
  {
    "checkName": "WORST RESPONSE TIME",
    "badResultInput": {
      "name": "badResult",
      "type": "number",
      "defaultValue": 1200,
      "placeholder": "The worst response time",
      "required": false,
      "format": "ms",
      "allowDecimals": false,
      "min": 100
    },
    "badResult": 1200,
    "badIncrementInput": {
      "name": "badIncrement",
      "type": "number",
      "placeholder": "The worst response time",
      "required": false,
      "format": "times",
      "allowDecimals": true,
      "min": 1.05
    },
    "isToggleOn": true
  }
]
```
The sample JSON file at the right of the page presents the Response Body obtained with the Sample Request.

### Sample Response Headers
```json
{
  "access-control-allow-headers": "Content-Type, Last-Update",
  "access-control-allow-methods": "POST, GET, OPTIONS, PUT, DELETE",
  "access-control-allow-origin": "*",
  "cache-control": "no-cache, private, no-store",
  "connection": "keep-alive",
  "content-encoding": "gzip",
  "content-type": "application/json;charset=utf-8",
  "date": "Wed, 23 Jun 2021 17:57:46 GMT",
  "expires": "Wed, 23 Jun 2021 17:57:46 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## PUT /HEALTH-CHECKS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG
<p class="put-endpoint">PUT</p> 

### Summary
The **PUT /HEALTH-CHECKS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG** endpoint updates the Health Checks confifguration of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/health-checks/projects/{project}/testcases/{testcase}/config''
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case | Yes | String |
| body | body | The JSON file with the object data for the Health check to edit. | Yes | JSON file |

> body parameter content example

```json
{
  "checkName": "AVG RESPONSE TIME",
  "badResult": 950,
  "badIncrement": 2,
  "isToggleOn": true
}
``` 

</br>

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description | Expected Values |
| --------- | -------- | ---- | ----------- | --------------- |
| checkName | yes | String | The name of the Health Check. | "AVG RESPONSE TIME" |
| | | | | "SUCC VS FAILED" |
| | | | | "WORST RESPONSE TIME" |
| badResult | yes | Integer | The value at what the result is considered bad. | Above 99 |
| badIncrement | yes | Integer | The number increment times value a result is considered bad. | Above 1 |
| isToggleOn | yes | Boolean| The indicator of wether the Health Check is activated or not. | true or false |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Updated |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "checkName": "AVG RESPONSE TIME", \ 
   "badResult": 950, \ 
   "badIncrement": 2, \ 
   "isToggleOn": true \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/health-checks/projects/seed-project/testcases/get-an-url/config'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/health-checks/projects/seed-project/testcases/get-an-url/config` 

### Sample Response Body
```json
true
```
The sample JSON file at the right of the page presents the Response Body obtained with the Sample Request.

### Sample Response Headers
```json
{
  "access-control-allow-headers": "Content-Type, Last-Update",
  "access-control-allow-methods": "POST, GET, OPTIONS, PUT, DELETE",
  "access-control-allow-origin": "*",
  "cache-control": "no-cache, private, no-store",
  "connection": "keep-alive",
  "content-length": "4",
  "content-type": "application/json;charset=utf-8",
  "date": "Wed, 23 Jun 2021 18:24:37 GMT",
  "expires": "Wed, 23 Jun 2021 18:24:37 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


