# Binaries
The Binaries resource enables you to interact with the Test Case Presets in Jeeves.
The following table describes the available endpoints of the Binaries resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-binaries" class="get-endpoint-word">GET</a> /binaries | Retrieves the name of the Presets available to create a Test Case. |

## GET /BINARIES
<p class="get-endpoint">GET</p>

### Summary 
The **GET /BINARIES** endpoint retrieves the name of the Presets available to create a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/binaries'
```

This endpoint does not allow extra parameters.

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |


### Sample Request
These are examples of an API request to this endpoint: 

#### cURL
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/binaries'`

#### Request URL
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/binaries`

### Sample Response Body

```json
[
  "GetASingleDynamicUrl",
  "GetASingleUrl",
  "GetASingleUrlChangingAHeaderValue",
  "GetASingleUrlChangingAPathParameter",
  "GetASingleUrlChangingAQueryValue",
  "GetASingleUrlFromDifferentHosts",
  "PostToASingleUrl",
  "PostToASingleUrlChangingAQueryValue"
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
  "date": "Fri, 18 Jun 2021 20:48:23 GMT",
  "expires": "Fri, 18 Jun 2021 20:48:23 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  ```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


