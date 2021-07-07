# Projects
The Projects resource enables you to interact with the Project profiles in Watson.
The following table describes the available endpoints of the Projects resource:


| Endpoint | Description |
| -------- | ----------- |
| <a href="#get-projects" class="get-endpoint-word">GET</a> /projects | Retrieves the data objects of the Project profiles available in Watson. |
| <a href="#post-projects" class="post-endpoint-word">POST</a> /projects | Creates a new Project profile. |
| <a href="#put-projects-project" class="put-endpoint-word">PUT</a> /projects/{project} | Updates the data object of a Project profile. |
| <a href="#delete-projects-project" class="delete-endpoint-word">DELETE</a> /projects/{project} | Deletes a Project profile. |


## GET /PROJECTS
<p class="get-endpoint">GET</p>

### Summary
The **GET /PROJECTS** endpoint retrieves the data objects of the Project profiles available in Watson. 

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 
'{API Environment URL}/projects?from={from}&size={size}'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| from | Query | The Project identification number | No | Integer |
| size | Query | The number of Projects to retrieve. | No | Integer |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://watson-nonprod.com/api/projects?from=0&size=2'`

#### HTTP Request
` http://watson-nonprod.com/api/projects?from=0&size=2 `



### Sample Response Body
```json
{
  "total": 27,
  "from": 0,
  "pageSize": 2,
  "results": [
    {
      "project": "Test-Project",
      "projectTeam": "Test Team",
      "projectBu": "Test BU",
      "projectRepository": "Test Repo",
      "lastActivity": 1623427403030,
      "timestamp": 1582927868192
    },
    {
      "project": "Allesseh.Ingest",
      "projectTeam": "Allesseh",
      "projectBu": "Allesseh",
      "projectRepository": "git@github.dowjones.net:Content/Allesseh.Ingest.git",
      "lastActivity": 1623349358757,
      "timestamp": 1622645743073
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
  "date": "Fri, 18 Jun 2021 03:49:02 GMT",
  "expires": "Fri, 18 Jun 2021 03:49:02 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


<a href="#projects" class="go-back"> ← Go back to the Projects resource page </a>



## POST /PROJECTS
<p class="post-endpoint">POST</p> 

### Summary 
The **POST /PROJECTS** endpoint creates a new Project profile.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/projects'
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | Body | The object data with the new Project profile details | Yes | JSON file | 

</br>
> body parameter content example

```json
 {
  "name": "new-project",
  "team": "Project Team",
  "bu": "Project Business Unit",
  "repository": "github.seed.com"
}
``` 
This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description |
| --------- | -------- | ---- | ----------- |
| name | Yes | String | The name of the Project |
| team | Yes | String | The name of the Project Team |
| bu | No | String | The Business Unit of the Team |
| repository | No | String | The URL to the Project repository |


### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "name": "new-project", \ 
   "team": "Project Team", \ 
   "bu": "Project Business Unit", \ 
   "repository": "github.seed.com" \ 
 }' 'http://watson-nonprod.com/api/projects'`

#### HTTP Request
`http://watson-nonprod.com/api/projects`
 

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
  "date": "Fri, 18 Jun 2021 14:12:24 GMT",
  "expires": "Fri, 18 Jun 2021 14:12:24 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



<a href="#projects" class="go-back"> ← Go back to the Projects resource page </a>



## PUT PROJECTS/{PROJECT}
<p class="put-endpoint">PUT</p> 

### Summary 
The **PUT PROJECTS/{PROJECT}** endpoint updates the data object of a Project profile.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/projects/{project}'
 ```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The current Project details | Yes | String |
| body | Body | The data object with the updated Project details | Yes | JSON file |

</br>

> body parameter content example

```json
 {
  "name": "seed-project",
  "team": "The Seed Team",
  "bu": "Plant Business Unit",
  "repository": "github.seed.com"
}
``` 

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description |
| --------- | -------- | ---- | ----------- |
| name | Yes | String | The name of the Project |
| team | Yes | String | The name of the Project Team |
| bu | Yes | String | The Business Unit of the Team |
| repository | No | String | The URL to the Project repository |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "name": "seed-project", \ 
   "team": "Seed team", \ 
   "bu": "Business Seed Unit”, \ 
   "repository": "github.seed.com" \ 
 }' 'http://watson-nonprod.com/api/projects/new-project'`


#### HTTP Request
`http://watson-nonprod.com/api/projects/new-project`


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
  "date": "Fri, 18 Jun 2021 15:33:05 GMT",
  "expires": "Fri, 18 Jun 2021 15:33:05 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



<a href="#projects" class="go-back"> ← Go back to the Projects resource page </a>



## DELETE /PROJECTS/{PROJECT}
<p class="delete-endpoint">DELETE</p> 

### Summary 
The **DELETE /PROJECTS/{PROJECT}** endpoint deletes a Project profile.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X DELETE --header 'Accept: application/json' 
'{API Environment URL}/projects/{project}'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | Path | The name of the Project to delete | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X DELETE --header 'Accept: application/json' 
'http://watson-nonprod.com/api/projects/new-project'`

#### HTTP Request
`http://watson-nonprod.com/api/projects/new-project` `

### Sample Response Body
This endpoint does not have a response body.

### Sample Response Headers
```json
{
  "access-control-allow-headers": "Content-Type, Last-Update",
  "access-control-allow-methods": "POST, GET, OPTIONS, PUT, DELETE",
  "access-control-allow-origin": "*",
  "cache-control": "no-cache, private, no-store",
  "connection": "keep-alive",
  "content-length": "0",
  "date": "Fri, 18 Jun 2021 20:37:05 GMT",
  "expires": "Fri, 18 Jun 2021 20:37:05 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



<a href="#projects" class="go-back"> ← Go back to the Projects resource page </a>


