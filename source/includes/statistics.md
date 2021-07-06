# Statistics
The Statistics resource enables you to interact with the Statistics Forms files of a Test Case. The following table describes the available endpoints of the Statistics resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-statistics-projects-project-testcases-testcase" class="get-endpoint-word">GET</a> /statistics/projects/{project}/testcases/{testcase} | Retrieves the Statistics of a Test Case. |
| <a href="#get-statistics-projects-project-testcases-testcase-config" class="get-endpoint-word">GET</a>  /statistics/projects/{project}/testcases/{testcase}/config | Retrieves the Statistics configuration of a Test Case. |
| <a href="#put-statistics-projects-project-testcases-testcase-config" class="put-endpoint-word">PUT</a>  /statistics/projects/{project}/testcases/{testcase}/config | Updates the Statistics time configuration of a Test Case. |

## GET /STATISTICS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /STATISTICS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}** endpoint retrieves the Statistics of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/statistics/projects/{project}/testcases/{testcase}?{from}&{size}'
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |
| from | query | The start list number of the Run Statistics. | No | Integer |
| size | query | The amout of results to retrieve. | No | Integer |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/statistics/projects/seed-project/testcases/get-an-url?from=1&size=1'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/statistics/projects/seed-project/testcases/get-an-url?from=1&size=1` 

### Sample Response Body
```json
{
  "total": 2,
  "from": 1,
  "pageSize": 1,
  "results": [
    {
      "timestamp": 1624461533724,
      "name": "getasingleurl-20210623152155525",
      "total": 345,
      "ok": 345,
      "failed": 0,
      "min": 4,
      "max": 100,
      "mean": 13,
      "responseTimeLowerBound": 800,
      "responseTimeHigherBound": 1200,
      "responseTimeout": 30000,
      "responsesUnderLowerBound": 345,
      "responsesUnderHigherBound": 0,
      "responsesAboveHigherBound": 0,
      "healthChecksTotal": 3,
      "healthChecksOk": 3,
      "healthChecksWarning": 0,
      "healthChecksFailed": 0
    }
  ]
}
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
  "date": "Wed, 23 Jun 2021 17:28:50 GMT",
  "expires": "Wed, 23 Jun 2021 17:28:50 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## GET /STATISTICS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /STATISTICS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG** endpoint retrieves the Statistics configuration of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/statistics/projects/{project}/testcases/{testcase}/config'
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success|

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/statistics/projects/seed-project/testcases/get-an-url/config'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/statistics/projects/seed-project/testcases/get-an-url/config` 

### Sample Response Body
```json
{
  "reponseTimeLowerBound": 800,
  "reponseTimeHigherBound": 1200,
  "responseTimeout": 30000,
  "inputs": [
    {
      "name": "reponseTimeLowerBound",
      "type": "number",
      "defaultValue": 800,
      "placeholder": "Delimiter for the first group in the time ranges chart, where t < lowerBound",
      "required": true,
      "format": "ms",
      "allowDecimals": false,
      "min": 100
    },
    {
      "name": "reponseTimeHigherBound",
      "type": "number",
      "defaultValue": 1200,
      "placeholder": "Delimiter for the second group in the time ranges chart, where lowerBound < t < higherBound",
      "required": true,
      "format": "ms",
      "allowDecimals": false,
      "min": 100
    },
    {
      "name": "responseTimeout",
      "type": "number",
      "defaultValue": 30000,
      "placeholder": "Period for which a request with no activity is considered a failure",
      "required": true,
      "format": "ms",
      "allowDecimals": false,
      "min": 100
    }
  ],
  "timestamp": -1
}
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
  "date": "Wed, 23 Jun 2021 17:38:16 GMT",
  "expires": "Wed, 23 Jun 2021 17:38:16 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





## PUT /STATISTICS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG
<p class="put-endpoint">PUT</p> 

### Summary 
The **PUT /STATISTICS/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/CONFIG** endpoint
updates the Statistics time configuration of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/statistics/projects/{project}/testcases/{testcase}/config'
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |
| body | body | The JSON file with the data object of the Statistics configuration. | Yes | JSON file |

> body parameter content example

```json
{
  "reponseTimeLowerBound": 1000,
  "reponseTimeHigherBound": 10000,
  "responseTimeout": 10001
}
``` 

</br>

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description |
| --------- | -------- | ---- | ----------- |
| reponseTimeLowerBound | yes | Integer | The lowest expected time in which a request gets a response. |
| reponseTimeHigherBound | yes | Integer | The highest expected time in which a request gets a response. |
| responseTimeout | yes | Integer | The time in which a request is close because it did not get a response. |



### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "reponseTimeLowerBound": 1000, \ 
   "reponseTimeHigherBound": 10000, \ 
   "responseTimeout": 10001 \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/statistics/projects/seed-project/testcases/get-an-url/config'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/statistics/projects/seed-project/testcases/get-an-url/config` 

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
  "date": "Wed, 23 Jun 2021 17:42:52 GMT",
  "expires": "Wed, 23 Jun 2021 17:42:52 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.

