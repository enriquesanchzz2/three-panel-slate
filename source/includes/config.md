# Config
The Config resource enables you to interact with the Configuration Forms files of a Test Case.
The following table describes the available endpoints of the Config resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-config-projects-project-testcases-testcase-forms-preview" class="get-endpoint-word">GET</a>  /config/projects/{project}/testcases/{testcase}/forms/preview | Retreives the data objects of a Test Case configuration forms. |
| <a href="#get-config-projects-project-testcases-testcase-forms-form-preview" class="get-endpoint-word">GET</a> /config/projects/{project}/testcases/{testcase}/forms/{form}/preview | Retreives the data object of a Test Case specific configuration form. |
| <a href="#get-config-projects-project-testcases-testcase-forms-form-validation" class="get-endpoint-word">GET</a>  /config/projects/{project}/testcases/{testcase}/forms/{form}/validation | Retreives the data object with the valid values of a Test Case specific configuration form. |
| <a href="#post-config-projects-project-testcases-testcase-forms-form" class="post-endpoint-word">POST</a>  /config/projects/{project}/testcases/{testcase}/forms/{form} | of a Test Case specific configuration form. |
| <a href="#put-config-projects-project-testcases-testcase-forms" class="put-endpoint-word">PUT</a>  /config/projects/{project}/testcases/{testcase}/forms | Updates a Test Case Preset. |
| <a href="#put-config-projects-project-testcases-testcase-forms-form" class="put-endpoint-word">PUT</a>  /config/projects/{project}/testcases/{testcase}/forms/{form} | Updates the file with the data object of a Test Case specific configuration form. |

## GET CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/PREVIEW
<p class="get-endpoint">GET</p> 

### Summary 
The **GET CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/PREVIEW** endpoint retreives the data objects of a Test Case configuration forms.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/config/projects/{project}/testcases/{testcase}/forms/preview'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case to retrieve the configuration from.  | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/preview'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/preview` 

### Sample Response Body
```json
[
  {
    "binary": "GetASingleUrl",
    "name": "config",
    "extension": "json",
    "preview": "[\n\t{\n\t\t\"rps\": 10,\n\t\t\"rampup\": 30,\n\t\t\"duration\": 50,\n\t\t\"followRedirects\": false\n\t}\n]\n",
    "documents": [],
    "size": "84 bytes"
  },
  {
    "binary": "GetASingleUrl",
    "name": "url",
    "extension": "json",
    "preview": "[\r\n\t{\r\n\t\t\"url\": \"http://computer-database.gatling.io/computers\"\r\n\t}\r\n]",
    "documents": [],
    "size": "70 bytes"
  },
  {
    "binary": "GetASingleUrl",
    "name": "headers",
    "extension": "json",
    "preview": "[\r\n\t{\r\n\t\t\"key\": \"Accept\",\r\n\t\t\"value\": \"*/*\"\r\n\t},\r\n\t{\r\n\t\t\"key\": \"Accept-Language\",\r\n\t\t\"value\": \"en-US,en;q=0.5\"\r\n\t}\r\n]",
    "documents": [],
    "size": "117 bytes"
  },
  {
    "binary": "GetASingleUrl",
    "name": "expected-status",
    "extension": "json",
    "preview": "[\r\n\t{\r\n\t\t\"status\": 200\r\n\t},\r\n\t{\r\n\t\t\"status\": 201\r\n\t},\r\n\t{\r\n\t\t\"status\": 202\r\n\t},\r\n\t{\r\n\t\t\"status\": 203\r\n\t},\r\n\t{\r\n\t\t\"status\": 204\r\n\t},\r\n\t{\r\n\t\t\"status\": 205\r\n\t},\r\n\t{\r\n\t\t\"status\": 206\r\n\t},\r\n\t{\r\n\t\t\"status\":",
    "documents": [],
    "size": "341 bytes"
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
  "date": "Tue, 22 Jun 2021 21:48:11 GMT",
  "expires": "Tue, 22 Jun 2021 21:48:11 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}/PREVIEW
<p class="get-endpoint">GET</p> 

### Summary 
The **GET CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}/PREVIEW** endpoint retreives the data object of a Test Case specific configuration form.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/config/projects/{project}/testcases/{testcase}/forms/{form}/preview''
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project | Yes | String |
| testcase| path | The name of the Test Case | Yes | String |
| form | path | The name of the Configuration form | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/config/preview'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/config/preview
` 

### Sample Response Body
```json
{
  "binary": "GetASingleUrl",
  "name": "config",
  "extension": "json",
  "preview": "[\n\t{\n\t\t\"rps\": 10,\n\t\t\"rampup\": 30,\n\t\t\"duration\": 50,\n\t\t\"followRedirects\": false\n\t}\n]\n",
  "documents": [],
  "size": "84 bytes"
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
  "date": "Tue, 22 Jun 2021 21:57:52 GMT",
  "expires": "Tue, 22 Jun 2021 21:57:52 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}/VALIDATION
<p class="get-endpoint">GET</p> 

### Summary 
The **GET CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}/VALIDATION** endpoint retreives the data object with the valid values of a Test Case specific configuration form.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/config/projects/{project}/testcases/{testcase}/forms/{form}/validation'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |
| form | path | The name of the configuration form to retreive. | Yes | String |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/config/validation'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/config/validation` 

### Sample Response Body
```json
{
  "name": "config",
  "isArray": false,
  "inputs": [
    {
      "name": "rps",
      "type": "number",
      "placeholder": "The number of requests per second (RPS) to execute (1 to 360000)",
      "required": true,
      "format": "",
      "allowDecimals": false,
      "max": 360000,
      "min": 1
    },
    {
      "name": "rampup",
      "type": "number",
      "placeholder": "The ramp up time in seconds to reach the target RPS (0 to 7200)",
      "required": true,
      "format": "",
      "allowDecimals": false,
      "max": 7200,
      "min": 0
    },
    {
      "name": "duration",
      "type": "number",
      "placeholder": "The time in seconds to complete de test case (5 to 7200)",
      "required": true,
      "format": "",
      "allowDecimals": false,
      "max": 7200,
      "min": 5
    },
    {
      "name": "followRedirects",
      "type": "checkbox",
      "placeholder": "",
      "required": false
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
  "date": "Tue, 22 Jun 2021 22:05:42 GMT",
  "expires": "Tue, 22 Jun 2021 22:05:42 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```

The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## POST CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}
<p class="post-endpoint">POST</p> 

### Summary 
The **POST CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}** endpoint uploads the file with the data object of a Test Case specific configuration form.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X POST --header 'Content-Type: multipart/form-data' --header 'Accept: application/json' {"type":"formData"} '{API Environment URL}/config/projects/{project}/testcases/{testcase}/forms/{form}'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |
| form | path | The name of the Configuration Form to edit. | Yes | String |
| file | formData | The JSON file with the data object for the Configuration Form. | Yes | JSON file |

</br>

To know more about the content of the Form files, see the User Guide section of Run Parameters. 

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Uploaded |


### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X POST --header 'Content-Type: multipart/form-data' --header 'Accept: application/json' {"type":"formData"} 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/url'
'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/url` 


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
  "date": "Tue, 22 Jun 2021 22:11:45 GMT",
  "expires": "Tue, 22 Jun 2021 22:11:45 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## PUT CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS
<p class="put-endpoint">PUT</p> 

### Summary 
The **PUT CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS** endpoint updates a Test Case Preset.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "binary": "PostToASingleUrl" \ 
 }' '{API Environment URL}/config/projects/{project}/testcases/{target}/forms'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case to update the Preset. | Yes | String |
| body | body | The JSON file with the data object for the Test Case Preset. | Yes | JSON file |


> body parameter content example

```json
 {
  "binary": "PostToASingleUrl"
 }
``` 
This tables lists the parameters of the body JSON file:

| Parameter | Required | Type |Description |
| ---- | ---------- | ----------- | -------- |
| binary | yes | String | The name of the Test Case Preset. |


### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Success|

### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "binary": "PostToASingleUrl" \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms` 

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
  "date": "Mon, 21 Jun 2021 22:00:12 GMT",
  "expires": "Mon, 21 Jun 2021 22:00:12 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## PUT CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}
<p class="put-endpoint">PUT</p> 

### Summary 
The **PUT CONFIG/PROJECTS/{PROJECT}/TESTCASES/{TESTCASE}/FORMS/{FORM}** endpoint updates the file with the data object of a Test Case specific configuration form.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
  "url": "http://www.wsj.com/" \ 
 } \ 
 ' '{API Environment URL}/config/projects/{project}/testcases/{testcase}/forms/{form}'

```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | String |
| testcase | path | The name of the Test Case. | Yes | String |
| form | path | The name of the Configuration Form. | Yes | String |
| body | body | The JSON file with the data object for the Configuration Form update. | Yes | JSON file |


</br>

To know more about the content of the Form files, see the User Guide section of Run Parameters. 

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 201 | Created |


### Sample Request
These are examples of an API request to this endpoint: 

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
  "url": "http://www.wsj.com/" \ 
 } \ 
 ' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/url'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/config/projects/seed-project/testcases/get-an-url/forms/url` 


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
  "date": "Tue, 22 Jun 2021 22:36:53 GMT",
  "expires": "Tue, 22 Jun 2021 22:36:53 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





