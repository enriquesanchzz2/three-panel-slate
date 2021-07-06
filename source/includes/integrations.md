# Integrations
The Integrations resource enables you to interact with the Integration configuration files of a Test Case. The following table describes the available endpoints of the Integration resource:

| Endpoint | Endpoint Description |
| -------- | -------------------- |
| <a href="#get-integrations-projects-project-slack-channel-notifier" class="get-endpoint-word">GET</a>  /integrations/projects/{project}/slack/channel-notifier |  Retrieves the Integrations confifguration file of a Test Case. |
| <a href="#put-integrations-projects-project-slack-channel-notifier" class="put-endpoint-word">PUT</a>   /integrations/projects/{project}/slack/channel-notifier | Updates the Integrations confifguration file of a Test Case. |

## GET /INTEGRATIONS/PROJECTS/{PROJECT}/SLACK/CHANNEL-NOTIFIER
<p class="get-endpoint">GET</p> 

### Summary
The **GET /INTEGRATIONS/PROJECTS/{PROJECT}/SLACK/CHANNEL-NOTIFIER** endpoint retrieves the Integrations confifguration file of a Test Case.

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X GET --header 'Accept: application/json' '{API Environment URL}/integrations/projects/{project}/slack/channel-notifier'
``` 

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project. | Yes | string |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Success |


### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X GET --header 'Accept: application/json' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/integrations/projects/seed-project/slack/channel-notifier'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/integrations/projects/seed-project/slack/channel-notifier` 

### Sample Response Body
```json
{
  "channelName": "test-jeeves-slack",
  "webhookUrl": true,
  "notificationTrigger": "WARNING",
  "alertTrigger": "BAD",
  "inputs": [
    {
      "name": "channelName",
      "type": "string",
      "placeholder": "The name of the slack channel.",
      "required": true,
      "secret": false,
      "pattern": "[[a-z]|[0-9]|[-_]]*",
      "maxlength": 21
    },
    {
      "name": "webhookUrl",
      "type": "string",
      "defaultValue": "",
      "placeholder": "The Webhook URL with the permits to publish in the slack channel.",
      "required": false,
      "secret": true,
      "pattern": "^(https?)://[-a-zA-Z0-9+&@#/%?=~_|!:,.;]*[-a-zA-Z0-9+&@#/%=~_|]",
      "maxlength": 2083
    },
    {
      "name": "notificationTrigger",
      "type": "select",
      "defaultValue": "WARNING",
      "placeholder": "The trigger for the status notification.",
      "required": true,
      "options": [
        "OK",
        "WARNING",
        "BAD",
        "NONE"
      ]
    },
    {
      "name": "alertTrigger",
      "type": "select",
      "defaultValue": "BAD",
      "placeholder": "The trigger for the @channel alert.",
      "required": true,
      "options": [
        "OK",
        "WARNING",
        "BAD",
        "NONE"
      ]
    }
  ],
  "timestamp": 1624473672714
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
  "date": "Wed, 23 Jun 2021 18:41:18 GMT",
  "expires": "Wed, 23 Jun 2021 18:41:18 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0",
  "transfer-encoding": "chunked"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.




## PUT /INTEGRATIONS/PROJECTS/{PROJECT}/SLACK/CHANNEL-NOTIFIER
<p class="put-endpoint">PUT</p> 

### Summary
The **PUT /INTEGRATIONS/PROJECTS/{PROJECT}/SLACK/CHANNEL-NOTIFIER** enpoint updates the Integrations confifguration file of a Test Case. 

### Parameters
> Use this cURL to make a request to this endpoint

```shell
curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{body}' '{API Environment URL}/integrations/projects/{project}/slack/channel-notifier'
```

This endpoint allows the following parameters:

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| project | path | The name of the Project with the Test Case. | Yes | string |
| body | body | The JSON file with the data object for the Slack integration. | Yes | JSON file |

> body parameter content example

```json
{
  "channelName": "test-jeeves-slack",
  "webhookUrl": "https://hooks.slack.com/services/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",
  "notificationTrigger": "OK",
  "alertTrigger": "WARNING"
}
``` 

</br>

This tables lists the parameters of the body JSON file:

| Parameter | Required | Type | Description | Expected Values |
| --------- | -------- | ---- | ----------- | --------------- |
| channelName | yes | String | The name of the Slack channel for the notifications. | The Slack channel name witouth the # symbol |
| webhookUrl | yes | String | The WebHook URL to integrate Jeeves to Slack. | https://hooks.slack.com/services/{Slack WebHook ID} |
| notificationTrigger | String | Integer | The type of success that triggers a notification. | "OK"</br>"WARNING"</br>"BAD"</br>"NONE" |
| alertTrigger | String | String | The type of success that triggers an alert. | "OK"</br>"WARNING"</br>"BAD"</br>"NONE" |

### Responses
This endpoint receives the following response code:

| Code | Description |
| ---- | ----------- |
| 200 | Updated |

### Sample Request
These are examples of an API request to this endpoint:

#### cURL Request
`curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "channelName": "test-jeeves-slack", \ 
   "webhookUrl": "https://hooks.slack.com/services/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", \ 
   "notificationTrigger": "OK", \ 
   "alertTrigger": "WARNING" \ 
 }' 'http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/integrations/projects/seed-project/slack/channel-notifier'`

#### HTTP Request
`http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api/integrations/projects/seed-project/slack/channel-notifier` 

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
  "date": "Wed, 23 Jun 2021 18:52:44 GMT",
  "expires": "Wed, 23 Jun 2021 18:52:44 GMT",
  "pragma": "no-cache",
  "server": "nginx/1.18.0"
}
```
The sample JSON file at the right of the page presents the Response Headers obtained with the Sample Request.


