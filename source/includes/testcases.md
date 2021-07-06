# Test Cases
The Test Cases resource enables you to interact with the Test Cases of a Project profile in Jeeves.
The following table describes the available endpoints of the Test Cases resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-projects-project-testcases" class="get-endpoint-word">GET</a> /projects/{project}/testcases | Retrieves the Test Cases of a Project profile. |
| <a href="#post-projects-project-testcases" class="post-endpoint-word">POST</a> /projects/{project}/testcases | Creates a new Test Case. |
| <a href="#delete-projects-project-testcases" class="delete-endpoint-word">DELETE</a> /projects/{project}/testcases | Deletes all Test Cases of a Project profile. |
| <a href="#get-projects-project-testcases-testcase" class="get-endpoint-word">GET</a> /projects/{project}/testcases/{testcase}	| Retrieves a Test Case data object. |
| <a href="#post-projects-project-testcases-testcase" class="post-endpoint-word">POST</a> /projects/{project}/testcases/{testcase} | Duplicates a Test Case. |
| <a href="#put-projects-project-testcases-testcase" class="put-endpoint-word">PUT</a> /projects/{project}/testcases/{testcase} | Updates a Test Case. |
| <a href="#delete-projects-project-testcases-testcase" class="delete-endpoint-word">DELETE</a> /projects/{project}/testcases/{testcase} | Deletes a Test Case. |


## GET/ PROJECTS/{PROJECT}/TESTCASES
<p class="get-endpoint">GET</p>

### Summary 
The **GET/ PROJECTS/{PROJECT}/TESTCASES** endpoint retrieves the Test Cases of a Project profile.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/projects/{project}/testcases?{from}&{size}'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project to retreive Test Cases from. | Yes | String |
| from | Query | The Test Case identification number. | No | Integer |
| size | Query | The number of Projects to retrieve. | No | Integer |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:  

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases?from=0&size=1'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases?from=0&size=1`

### Sample Response Body

```json
{
  "access-control-allow-headers": "Content-Type, Last-Update",
  "access-control-allow-methods": "POST, GET, OPTIONS, PUT, DELETE",
  "access-control-allow-origin": "*",
  "cache-control": "no-cache, private, no-store",
  "connection": "keep-alive",
  "content-encoding": "gzip",
  "content-type": "application/json;charset=utf-8",
  "date": "Mon, 21 Jun 2021 15:22:48 GMT",
  "expires": "Mon, 21 Jun 2021 15:22:48 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
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
  "date": "Tue, 22 Jun 2021 19:46:44 GMT",
  "expires": "Tue, 22 Jun 2021 19:46:44 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## POST /PROJECTS/{PROJECT}/TESTCASES
<p class="post-endpoint">POST</p> 

### Summary 
The **POST /PROJECTS/{PROJECT}/TESTCASE** endpoint Creates a new Test Case. 

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/projects/{project}/testcases''
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project to create the Test Case | Yes | String |
| body | Body | The JSON file with the data object to create the Test Case | Yes | JSON file |

</br>

> Body Parameter content example

```json
{
  "name": "get-a-url",
  "description": "Tests an URL",
  "binary": "GetASingleUrl"
}
```

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description |
| --------- | -------- | ---- | ----------- |
| name | Yes | String | The name of the Test Case |
| description | No | String | The description of the Test Case |
| binary | Yes | String | The Preset for the Test Case |


### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |


### Sample Request
These are examples of an API request to this endpoint:  

#### cURL Request
`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "name": "get-a-url", \ 
   "description": "Tests an URL", \ 
   "binary": "GetASingleUrl" \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases` 

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
  "date": "Tue, 22 Jun 2021 19:52:50 GMT",
  "expires": "Tue, 22 Jun 2021 19:52:50 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





## DELETE /PROJECTS/{PROJECT}/TESTCASES
<p class="delete-endpoint">DELETE</p> 

### Summary 
The **DELETE /PROJECTS/{PROJECT}/TESTCASES** endpoint deletes all Test Cases of a Project profile.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X DELETE --header 'Accept: application/json' '{API Environment URL}/projects/{project}/testcases'
'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project to delete all Test Cases. | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:  

#### cURL Request
`curl -X DELETE --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/jeeves-api/testcases'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/jeeves-api/testcases` 

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
  "date": "Tue, 22 Jun 2021 19:57:41 GMT",
  "expires": "Tue, 22 Jun 2021 19:57:41 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}
<p class="get-endpoint">GET</p>

### Summary 
The **GET /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}** endpoint retrieves a Test Case data object.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/projects/{project}/testcases/{testcase}'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project with the Test Case. | Yes | String |
| testcase | Path | The name of the Test Case to retrieve. | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:  

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/get-an-url'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/get-an-url`

### Sample Response Body
```json
{
  "testcase": "get-an-url",
  "project": "seed-project",
  "binary": "GetASingleUrl",
  "description": "get-an-url",
  "lastActivity": 1624392124576,
  "timestamp": 1624392124576,
  "isRunning": false,
  "isPending": false,
  "latestStatistic": {
    "timestamp": -1,
    "name": "",
    "total": 0,
    "ok": 0,
    "failed": 0,
    "min": 0,
    "max": 0,
    "mean": 0,
    "responseTimeLowerBound": 800,
    "responseTimeHigherBound": 800,
    "responseTimeout": 800
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
  "date": "Tue, 22 Jun 2021 20:02:19 GMT",
  "expires": "Tue, 22 Jun 2021 20:02:19 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```

The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## POST /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}
<p class="post-endpoint">POST</p> 

### Summary 
The **POST /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}** endpoint Duplicates a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/projects/{project}/testcases/{testcase}'
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project with the Test Case. | Yes | String |
| testcase | Path | The name of the Test Case to duplicate. | Yes | String |
| body | Body | The JSON file with the data object for the Test Case. | Yes | JSON file |

</br>

> Body Parameter content example

```json
{
  "name": "copy-of-get-a-url",
  "description": "A copy of the get an url Test Case",
}
```

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description |
| --------- | -------- | ---- | ----------- |
| name | Yes | String | The name of the Test Case duplicate |
| description | No | String | The description of the Test Case duplicate |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint:  

#### cURL Request
`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "name": "copy-of-get-an-url", \ 
   "description": "A copy of the get an url Test Case" \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/get-an-url'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/get-an-url` 

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
  "date": "Tue, 22 Jun 2021 20:09:37 GMT",
  "expires": "Tue, 22 Jun 2021 20:09:37 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## PUT /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}
<p class="put-endpoint">PUT</p> 

### Summary
The **PUT /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}** endpoint updates a Test Case. 

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/{project}/testcases/{testcase}'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project with the Test Case. | Yes | String |
| testcase | Path | The name of the Test Case to update. | Yes | String |
| body | Body | The JSON file with the data object of the Test Case. | Yes | JSON file |

</br>

> Body Parameter content example

```json
{
  "name": "get-an-url-2",
  "description": "A copy of the Get an URL Test Case"
}
```

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description |
| --------- | -------- | ---- | ----------- |
| name | Yes | String | The new name of the Test Case |
| description | No | String | The new description of the Test Case |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint:  

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "name": "get-an-url-2", \ 
   "description": "A copy of the Get an URL Test Case" \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/copy-of-get-an-url'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/copy-of-get-an-url` 

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
  "date": "Tue, 22 Jun 2021 21:26:46 GMT",
  "expires": "Tue, 22 Jun 2021 21:26:46 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## DELETE /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}
<p class="delete-endpoint">DELETE</p> 

**Summary:**
The **DELETE /PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}** endpoint deletes a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X DELETE --header 'Accept: application/json' '{API Environment URL}/projects/{project}/testcases/{testcase}'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project with the Test Case. | Yes | String |
| testcase | Path | The name of the Test Case to delete. | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:  

#### cURL Request
`curl -X DELETE --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/get-an-url-2'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/testcases/get-an-url-2` 

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
  "date": "Tue, 22 Jun 2021 21:32:08 GMT",
  "expires": "Tue, 22 Jun 2021 21:32:08 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


