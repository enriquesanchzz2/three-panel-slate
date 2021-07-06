# Runner
The Runner resource enables you to interact the Test Cases. The following table describes the available endpoints of the Runner resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-runner-projects-project-testcases-testcase-run" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{testcase}/run | Runs a specific Test Case. |
| <a href="#get-runner-projects-project-testcases-testcase-status" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{test case}/status | Retrieves the Run Status of a Test Case. | 
| <a href="#get-runner-projects-project-testcases-testcase-stop" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{testcase}/stop  | Stops the Run task of a Test Case. |
| <a href="#get-runner-status" class="get-endpoint-word">GET</a> /runner/status | Retrieves the status of the active and pending Test Cases. |
| <a href="#get-runner-projects-project-testcases-testcase-options" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{testcase}/options | Retrieves the Run Agent configuration of a Test Case. |
| <a href="#put-runner-projects-project-testcases-testcase-options" class="put-endpoint-word">PUT</a> /runner/projects/{project}/testcases/{testcase}/options | Updates the Run Agent configuration of a Test Case. |

## GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/RUN
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/RUN** endpoint runs a specific Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/api/runner/projects/{project}/testcases/{testcase}/run'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Test Case Project. | Yes | String |
| testcase | path | The name of the Target Test Case | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/run'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/run` 


### Sample Response Body
```json
"jeeves.core.model.impl.runagents.FleetObserver@2cc70ca8"
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
  "content-length": "57",
  "content-type": "application/json;charset=utf-8",
  "date": "Wed, 23 Jun 2021 15:18:53 GMT",
  "expires": "Wed, 23 Jun 2021 15:18:53 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET /RUNNER/STATUS
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /RUNNER/STATUS** endpoint retrieves the status of the active and pending Test Cases.

### Parameters
This endpoint does not allow extra parameters. 

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/status'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/status` 


### Sample Response Body
```json
{
  "timestamp": 1624557854639,
  "activeTasks": {
    "size": 0,
    "maxSize": 100,
    "all": []
  },
  "pendingTasks": {
    "size": 0,
    "maxSize": 100,
    "all": []
  }
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
  "date": "Thu, 24 Jun 2021 18:04:14 GMT",
  "expires": "Thu, 24 Jun 2021 18:04:14 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/STATUS
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/STATUS** endpoint retrieves the Run Status of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/runner/projects/{project}/testcases/{testcase}/status'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Test Case Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/status'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/status` 



### Sample Response Body
```json
{
  "logs": "[RUN AGENT] Joining the pending queue...   # 1 second after launch\n[RUN AGENT] Executing run command...   # 1 second after launch\n[RUN AGENT] Requesting spot fleet...\n[RUN AGENT] Launched fleet with 1 spots \n[RUN AGENT] Run command successfully executed\n",
  "isRunning": true,
  "isPending": false,
  "timestamp": 1624462776743,
  "lastActivity": 1624462779799
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
  "date": "Wed, 23 Jun 2021 15:39:44 GMT",
  "expires": "Wed, 23 Jun 2021 15:39:44 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/STOP
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/STOP** endpoint stops the Run task of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/runner/projects/{project}/testcases/{testcase}/stop'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Test Case Project. | Yes | String |
| testcase | path | The name of the Test Case | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/stop'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/stop` 


### Sample Response Body
This endpoint does not have a Response Body.

### Sample Response Headers
```json
{
  "access-control-allow-headers": "Content-Type, Last-Update",
  "access-control-allow-methods": "POST, GET, OPTIONS, PUT, DELETE",
  "access-control-allow-origin": "*",
  "cache-control": "no-cache, private, no-store",
  "connection": "keep-alive",
  "content-length": "0",
  "date": "Wed, 23 Jun 2021 16:10:09 GMT",
  "expires": "Wed, 23 Jun 2021 16:10:09 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/OPTIONS
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/OPTIONS** endpoint retrieves the Run Agent configuration of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/runner/projects/{project}/testcases/{testcase}/options'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Test Case Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/options'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/options` 


### Sample Response Body
```json

[
  {
    "currentValue": 1,
    "inputSpec": {
      "name": "peers",
      "type": "number",
      "defaultValue": 1,
      "placeholder": "The workload will be multiplied by the number of peer nodes",
      "required": true,
      "format": "",
      "allowDecimals": false,
      "max": 20,
      "min": 1
    }
  },
  {
    "currentValue": "https://status.aws.amazon.com/",
    "inputSpec": {
      "name": "warmup-url",
      "type": "string",
      "defaultValue": "https://status.aws.amazon.com/",
      "placeholder": "This URL is requested to test network connectivity",
      "required": true,
      "secret": false,
      "pattern": "^(https?)://[-a-zA-Z0-9+&@#/%?=~_|!:,.;]*[-a-zA-Z0-9+&@#/%=~_|]",
      "maxlength": 2083
    }
  },
  {
    "currentValue": "t2.micro",
    "inputSpec": {
      "name": "spot-size",
      "type": "select",
      "defaultValue": "t2.micro",
      "placeholder": "Larger instance types support a higher network throughput, but their cost will be higher and they might also take longer to allocate",
      "required": true,
      "options": [
        "t2.micro",
        "t3.small",
        "t3.medium",
        "c4.large",
        "c5.large"
      ]
    }
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
  "date": "Wed, 23 Jun 2021 16:14:43 GMT",
  "expires": "Wed, 23 Jun 2021 16:14:43 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


## PUT /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/OPTIONS
<p class="put-endpoint">PUT</p> 

### Summary 
The **PUT /RUNNER/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/OPTIONS** endpoint updates the Run Agent configuration of a Test Case. 

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/runner/projects/{project}/testcases/{testcase}/options'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Test Case Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |
| body | body | The JSON file with the Object data for the Test Case Run Agent configuration.  | Yes | JSON file  |

> body parameter content example

```json
{
   "peers":1,
   "warmup-url":"https://www.google.com/",
   "spot-size":"t2.micro"
}
``` 

</br>

This tables lists the parameters of the body JSON file:

| Parameter | Required | Type |Description |
| ---- | ---------- | ----------- | -------- |
| peers | yes | Integer | The number of Spot Instances to run the Test Case. |
| warmup-url | yes | String | The Project main Host URL to test connectivity. |
| spot-size | yes | String | The name of the Spot Instances sizes. | 


### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
    "peers":1, \ 
    "warmup-url":"https://www.google.com/", \ 
    "spot-size":"t2.micro" \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/options'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/runner/projects/seed-project/testcases/get-an-url/options` 


### Sample Response Body
This endpoint does not have a Response Body.

### Sample Response Headers
```json
{
  "access-control-allow-headers": "Content-Type, Last-Update",
  "access-control-allow-methods": "POST, GET, OPTIONS, PUT, DELETE",
  "access-control-allow-origin": "*",
  "cache-control": "no-cache, private, no-store",
  "connection": "keep-alive",
  "content-length": "0",
  "date": "Wed, 23 Jun 2021 17:17:07 GMT",
  "expires": "Wed, 23 Jun 2021 17:17:07 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



