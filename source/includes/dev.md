# Dev
The Dev resource enables you to interact with the Configuration files of Jeeves. The following table describes the available endpoints of the Dev resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-dev-version" class="get-endpoint-word">GET</a>   /dev/version | Retrieves the current version of Jeeves. |
| <a href="#get-dev-run-agent" class="get-endpoint-word">GET</a>   /dev/run-agent | Retrieves the Run Agent details of Jeeves. |
| <a href="#get-dev-ec2" class="get-endpoint-word">GET</a>  /dev/ec2 | Retrieves the AWS Elasctic Spot Instances. |
| <a href="#get-dev-es" class="get-endpoint-word">GET</a>  /dev/es | Retrieves the AWS ElasticBeanstalk Instance. |
| <a href="#get-dev-s3" class="get-endpoint-word">GET</a>  /dev/s3 | Retrieves the AWS S3 Bucket information. |
| <a href="#get-dev-s3-project-testcase" class="get-endpoint-word">GET</a>  /dev/s3/{project}/{testcase} | Retrieves the AWS S3 Buckets Objects location. |
| <a href="#get-dev-json_header" class="get-endpoint-word">GET</a>  /dev/json_header | Retrieves the Accepts headers. |
| <a href="#get-dev-stop" class="get-endpoint-word">GET</a>  /dev/stop | Stops the Embeded Jetty Server of Jeeves. |
| <a href="#post-dev-json_post" class="post-endpoint-word">POST</a>  /dev/json_post | Verifies that the Content Type is a JSON. |

## GET /DEV/VERSION
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/VERSION** endpoint retrieves the current version of Jeeves.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/version'
```
This endpoint does not allow extra parameters.

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/version'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/version` 

### Sample Response Body
```json
{
  "version": "4.6.6"
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
  "date": "Thu, 24 Jun 2021 15:17:00 GMT",
  "expires": "Thu, 24 Jun 2021 15:17:00 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





## GET /DEV/RUN-AGENT
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/RUN-AGENT** endpoint retrieves the Run Agent details of Jeeves.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/run-agent'
```
This endpoint does not allow extra parameters.

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/run-agent'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/run-agent` 

### Sample Response Body
```json
{
  "name": "spot",
  "nameTag": "con.nonprod.shdsvc.ue1-nonprod"
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
  "date": "Thu, 24 Jun 2021 15:26:07 GMT",
  "expires": "Thu, 24 Jun 2021 15:26:07 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## GET /DEV/EC2
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/EC2** endpoint retrieves the AWS Elasctic Spot Instances.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/ec2'
```
This endpoint does not allow extra parameters.


### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/ec2'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/ec2` 

### Sample Response Body
```json
{
  "spot_tags": 7,
  "images": [
    {
      "name": "amigo-amzn_linux-2-dowjones-base-202105100930",
      "description": null,
      "type": "machine",
      "rootDeviceName": "/dev/xvda",
      "tags": ""
    }
  ],
  "subnets": [
    {
      "availabilityZone": "us-east-1d",
      "subnetTags": {
        "environment": "dev",
        "owner": "Chris.Tersteeg@dowjones.com",
        "bu": "djcs",
        "tier": "protected",
        "product": "consumer",
        "component": "sharsvc",
        "servicename": "djcs/consumer/sharsvc",
        "Name": "con.nonprod.shdsvc.ue1-nonprod-pro-1d"
      },
      "vpcTags": {
        "Name": "con.nonprod.shdsvc.ue1-nonprod",
        "bu": "djcs",
        "environment": "dev",
        "owner": "Chris.Tersteeg@dowjones.com",
        "product": "consumer",
        "component": "sharsvc",
        "servicename": "djcs/consumer/sharsvc"
      }
    },
    {
      "availabilityZone": "us-east-1b",
      "subnetTags": {
        "bu": "djcs",
        "environment": "dev",
        "Name": "con.nonprod.shdsvc.ue1-nonprod-pro-1b",
        "product": "consumer",
        "component": "sharsvc",
        "owner": "Chris.Tersteeg@dowjones.com",
        "servicename": "djcs/consumer/sharsvc",
        "tier": "protected"
      },
      "vpcTags": {
        "Name": "con.nonprod.shdsvc.ue1-nonprod",
        "bu": "djcs",
        "environment": "dev",
        "owner": "Chris.Tersteeg@dowjones.com",
        "product": "consumer",
        "component": "sharsvc",
        "servicename": "djcs/consumer/sharsvc"
      }
    },
    {
      "availabilityZone": "us-east-1a",
      "subnetTags": {
        "servicename": "djcs/consumer/sharsvc",
        "product": "consumer",
        "Name": "con.nonprod.shdsvc.ue1-nonprod-pro-1a",
        "bu": "djcs",
        "environment": "dev",
        "tier": "protected",
        "owner": "Chris.Tersteeg@dowjones.com",
        "component": "sharsvc"
      },
      "vpcTags": {
        "Name": "con.nonprod.shdsvc.ue1-nonprod",
        "bu": "djcs",
        "environment": "dev",
        "owner": "Chris.Tersteeg@dowjones.com",
        "product": "consumer",
        "component": "sharsvc",
        "servicename": "djcs/consumer/sharsvc"
      }
    }
  ],
  "fleetRequestHistory": [
    {
      "sfr-0b7bd8e4-fa0b-4106-ab8c-94eabfd0a630": "cancelled"
    },
    {
      "sfr-21a62414-cdaa-4d6e-90e3-cc189692f514": "cancelled"
    },
    {
      "sfr-36f926c7-b4dc-4065-b57c-4a991f8d4ab5": "cancelled"
    },
    {
      "sfr-40cb3437-50d0-4d2e-9448-f9f138528024": "cancelled"
    },
    {
      "sfr-438d36c0-900d-4b45-a2a2-6ab39d30f1a1": "cancelled"
    },
    {
      "sfr-709e8d59-fd86-4c8b-aa98-edd5953cc512": "cancelled"
    },
    {
      "sfr-9432bc05-1054-4db8-b6aa-d14074904636": "cancelled"
    },
    {
      "sfr-e47b4be5-dc44-43ce-8644-44fc01cd8e72": "active"
    },
    {
      "sfr-e957d0d3-dfde-4668-a226-fa8c5e885fe5": "cancelled"
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
  "date": "Thu, 24 Jun 2021 15:29:41 GMT",
  "expires": "Thu, 24 Jun 2021 15:29:41 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## GET /DEV/ES
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/ES** endpoint retrieves the AWS ElasticBeanstalk Instance.

### Responses
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/es'
```
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Parameters
This endpoint does not allow extra parameters.

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/es'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/es` 

### Sample Response Body
```json
{
  "domain": "djsp-connonprodshdsvc-jeeves",
  "cluster_name": "827737064932:djsp-connonprodshdsvc-jeeves",
  "tagline": "You Know, for Search"
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
  "date": "Thu, 24 Jun 2021 16:09:33 GMT",
  "expires": "Thu, 24 Jun 2021 16:09:33 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





## GET /DEV/S3
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/S3** endpoint retrieves the AWS S3 Bucket information.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/s3'
```
This endpoint does not allow extra parameters.

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/s3'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/s3` 

### Sample Response Body
```json
{
  "bucket": "djss-dev",
  "location": "s3Operations.getBucketLocation"
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
  "date": "Thu, 24 Jun 2021 16:10:49 GMT",
  "expires": "Thu, 24 Jun 2021 16:10:49 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.



## GET /DEV/S3/{PROJECT}/{TESTCASE}
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/S3/{PROJECT}/{TESTCASE}** endpoint retrieves the AWS S3 Buckets Objects location.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/s3/seed-project/get-an-url'
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
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/s3/seed-project/get-an-url'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/s3/seed-project/get-an-url` 


### Sample Response Body
```json
[
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/GetASingleUrl/data/config.json",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/GetASingleUrl/data/expected-status.json",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/GetASingleUrl/data/headers.json",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/GetASingleUrl/data/url.json",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/PostToASingleUrl/data/expected-status.json",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/PostToASingleUrl/data/headers.json",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/PostToASingleUrl/data/url.json",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/reports/getasingleurl-20210623152155525.zip",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/reports/getasingleurl-20210623154221156.zip",
  "djsp-connonprodshdsvc-jeeves/nonprod/testcases/u3RQNXoBiYo7k6xdyFy6/reports/getasingleurl-20210623194056265.zip"
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
  "date": "Thu, 24 Jun 2021 16:13:45 GMT",
  "expires": "Thu, 24 Jun 2021 16:13:45 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


## GET /DEV/JSON_HEADER
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/JSON_HEADER** endpoint retrieves the Accepts headers.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/json_header'
```
This endpoint does not allow extra parameters.

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/json_header'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/json_header` 

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
  "date": "Thu, 24 Jun 2021 16:20:29 GMT",
  "expires": "Thu, 24 Jun 2021 16:20:29 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.






## GET /DEV/STOP
<p class="get-endpoint">GET</p> 

### Summary 
The **GET /DEV/STOP** endpoint stops the Embeded Jetty Server of Jeeves.

### Parameters
This endpoint does not allow extra parameters.

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 404 | The server has stopped |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: text/plain' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/stop'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/stop` 

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
  "content-type": "text/plain;charset=utf-8",
  "date": "Thu, 24 Jun 2021 16:30:34 GMT",
  "expires": "Thu, 24 Jun 2021 16:30:34 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.





## POST /DEV/JSON_POST
<p class="post-endpoint">POST</p> 

### Summary 
The **POST /DEV/JSON_POST** endpoint verifies that the Content Type is a JSON.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "ok": true \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/json_post'
```
This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | The JSON file with the data object to set the Content Type. | Yes | JSON file |

> body parameter content example

```json
{
  "ok": true
}
``` 

</br>

This tables lists the parameters of the body JSON file:

| parameter | Required | Type | Description |
| --------- | -------- | ---- | ----------- |
| ok | yes | Boolean | indicates that the Content Type is a JSON. |



### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |


### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "ok": true \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/json_post'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/dev/json_post` 


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
  "date": "Thu, 24 Jun 2021 16:49:42 GMT",
  "expires": "Thu, 24 Jun 2021 16:49:42 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "content-type": null
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


