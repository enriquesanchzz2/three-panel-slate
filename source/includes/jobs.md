# Jobs
The Jobs resource enables you to interact with the Jobs tasks of a Project profile. The following table describes the available endpoints of the Jobs resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#post-jobs-start" class="post-endpoint-word">POST</a> /jobs/start | Starts a Project profile Job Run task. |
| <a href="#get-jobs-trackingnumber-status" class="get-endpoint-word">GET</a> /jobs/{trackingNumber}/status | Retrieves the status of a Project profile Job. |
| <a href="#get-jobs-trackingnumber-abort" class="get-endpoint-word">GET</a> /jobs/trackingNumber}/abort | Stops a Project profile Job Run task. |
| <a href="#get-projects-project-jobs" class="get-endpoint-word">GET</a> /projects/{project}/jobs | Retrieves the Jobs history of a Project profile. |


## POST /JOBS/START
<p class="post-endpoint">POST</p> 

### Summary
The **POST /JOBS/START** endpoint starts a Project profile Job Run task.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Enviroment URL}/jobs/start'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | The Json file with the data object to create the Job | Yes | JSON file |

> body parameter content example

```json
{
  "project": "seed-project",
  "executionNotes": "new-seed-job",
  "requireApprovingChecks": 2
}
``` 

</br>

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description | Expected Values |
| --------- | -------- | ---- | ----------- | --------------- |
| project | yes | String | The name of the Project to create a Job. | |
| executionNotes | yes | String | The name of the new Job. | |
| requireApprovingChecks | yes | Integer | The percentage of successful tasks at what a job is considered successful. | A number equal or less than a 100 </br> A number equal or greater than 0 |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "project": "seed-project", \ 
   "executionNotes": "new-seed-job", \ 
   "requireApprovingChecks": 2 \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/jobs/start'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/jobs/start` 

### Sample Response Body
```json
"83bb7b6ffc87d734c8a117d4c7e508a97e671e9adaf8d32c69530c78ccd959fb"
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
  "date": "Wed, 23 Jun 2021 19:38:36 GMT",
  "expires": "Wed, 23 Jun 2021 19:38:36 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





## GET /JOBS/{TRACKINGNUMBER}/STATUS
<p class="get-endpoint">GET</p> 

### Summary
The **GET /JOBS/{TRACKINGNUMBER}/STATUS** endpoint retrieves the status of a Project profile Job.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/jobs/{trackingNumber}/status'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| trackingNumber | path | The Tracking Number ID of the Project Job | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200| Success |


### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/jobs/83bb7b6ffc87d734c8a117d4c7e508a97e671e9adaf8d32c69530c78ccd959fb/status'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/jobs/83bb7b6ffc87d734c8a117d4c7e508a97e671e9adaf8d32c69530c78ccd959fb/status` 

### Sample Response Body
```json
{
  "trackingNumber": "83bb7b6ffc87d734c8a117d4c7e508a97e671e9adaf8d32c69530c78ccd959fb",
  "executionNotes": "new-seed-job",
  "totalTasks": 1,
  "terminatedTasks": 1,
  "isTerminated": true,
  "isOk": true,
  "timestamp": 1624477116759,
  "lastActivity": 1624477351093,
  "logs": "> Starting job for seed-project with 1 tasks\n   MIN SCORE = 2.0%\n\nget-an-url > Adding to run queue\nget-an-url > Finished execution\n\nSCORE = 100.0%\n"
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
  "date": "Wed, 23 Jun 2021 19:53:53 GMT",
  "expires": "Wed, 23 Jun 2021 19:53:53 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## GET /JOBS/{TRACKINGNUMBER}/ABORT
<p class="get-endpoint">GET</p> 

### Summary
The **GET /JOBS/{TRACKINGNUMBER}/ABORT** endpoint stops a Project profile Job Run task.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/jobs/{trackingNumber}/abort'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| trackingNumber | path | The Tracking Number ID of the Project Job | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/jobs/83bb7b6ffc87d734c8a117d4c7e508a97e671e9adaf8d32c69530c78ccd959fb/abort'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/jobs/83bb7b6ffc87d734c8a117d4c7e508a97e671e9adaf8d32c69530c78ccd959fb/abort` 

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
  "date": "Wed, 23 Jun 2021 19:57:49 GMT",
  "expires": "Wed, 23 Jun 2021 19:57:49 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





## GET /PROJECTS/{PROJECT}/JOBS
<p class="get-endpoint">GET</p> 

### Summary
The **GET /PROJECTS/{PROJECT}/JOBS** endpoint retrieves the Jobs history of a Project profile.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/projects/{project}/jobs?{from}&{size}'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| from | query | The list number ID of the Project Job. | No | integer |
| size | query | The amount of jobs data objects to retreive. | No | integer |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/jobs?from=0&size=1'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/projects/seed-project/jobs?from=0&size=1` 

### Sample Response Body
```json
{
  "total": 1,
  "from": 0,
  "pageSize": 1,
  "results": [
    {
      "trackingNumber": "83bb7b6ffc87d734c8a117d4c7e508a97e671e9adaf8d32c69530c78ccd959fb",
      "executionNotes": "new-seed-job",
      "totalTasks": 1,
      "terminatedTasks": 1,
      "isTerminated": true,
      "isOk": true,
      "timestamp": 1624477116759,
      "lastActivity": 1624477351093,
      "logs": "> Starting job for seed-project with 1 tasks\n   MIN SCORE = 2.0%\n\nget-an-url > Adding to run queue\nget-an-url > Finished execution\n\nSCORE = 100.0%\n"
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
  "date": "Thu, 24 Jun 2021 15:07:08 GMT",
  "expires": "Thu, 24 Jun 2021 15:07:08 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



