# Jeeves API Reference Documentation

Jeeves is a monitor tool that helps developers analyze a project’s web performance. With Jeeves, you can do the following:

  * Design Test Cases to validate service availability and throughput.
  * Group load Test Cases by Project profiles.
  * Run, stop, and reconfigure Test Cases to validate service availability.
  * Monitor a website performance through different Test Cases.
  * Obtain detailed reports with graphics about their website performance.
  

This documentation guides you through the resources, methods, and endpoints of the Jeeves API. It also contains examples of request bodies and responses, so that you can start working with the Jeeves API as smoothly as possible.


The following table contains the resources available in the Jeeves API:

| API Resource | Endpoint | Endpoint Description |
| ------------ | -------- | -------------------- |
| <a href="#projects"> **Projects**</a> | <a href="#get-projects" class="get-endpoint-word">GET</a> /projects | Retrieves the data objects of the Project profiles available in Jeeves. |
| | <a href="#post-projects" class="post-endpoint-word">POST</a> /projects | Creates a new Project profile. |
| | <a href="#put-projects-project" class="put-endpoint-word">PUT</a> /projects/{project} | Updates the data object of a Project profile. |
| | <a href="#delete-projects-project" class="delete-endpoint-word">DELETE</a> /projects/{project} | Deletes a Project profile. |
| <a href="#Binaries">**Binaries**</a> | <a href="#get-binaries" class="get-endpoint-word">GET</a> /binaries | Retrieves the name of the Presets available to create a Test Case. |
| <a href="#Test-Cases">**Test Cases**</a> | <a href="#get-projects-project-testcases" class="get-endpoint-word">GET</a> /projects/{project}/testcases | Retrieves the Test Cases of a Project profile. |
| | <a href="#post-projects-project-testcases" class="post-endpoint-word">POST</a> /projects/{project}/testcases | Creates a new Test Case. |
| | <a href="#delete-projects-project-testcases" class="delete-endpoint-word">DELETE</a> /projects/{project}/testcases | Deletes all Test Cases of a Project profile. |
| | <a href="#get-projects-project-testcases-testcase" class="get-endpoint-word">GET</a> /projects/{project}/testcases/{testcase}	| Retrieves a Test Case data object. |
| | <a href="#post-projects-project-testcases-testcase" class="post-endpoint-word">POST</a> /projects/{project}/testcases/{testcase} | Duplicates a Test Case. |
| | <a href="#put-projects-project-testcases-testcase" class="put-endpoint-word">PUT</a> /projects/{project}/testcases/{testcase} | Updates a Test Case. |
| | <a href="#delete-projects-project-testcases-testcase" class="delete-endpoint-word">DELETE</a> /projects/{project}/testcases/{testcase} | Deletes a Test Case. |
| <a href="#config">**Config**</a> | <a href="#get-config-projects-project-testcases-testcase-forms-preview" class="get-endpoint-word">GET</a>  /config/projects/{project}/testcases/{testcase}/forms/preview | Retreives the data objects of a Test Case configuration forms. |
| | <a href="#get-config-projects-project-testcases-testcase-forms-form-preview" class="get-endpoint-word">GET</a> /config/projects/{project}/testcases/{testcase}/forms/{form}/preview | Retreives the data object of a Test Case specific configuration form. |
| | <a href="#get-config-projects-project-testcases-testcase-forms-form-validation" class="get-endpoint-word">GET</a>  /config/projects/{project}/testcases/{testcase}/forms/{form}/validation | Retreives the data object with the valid values of a Test Case specific configuration form. |
| | <a href="#post-config-projects-project-testcases-testcase-forms-form" class="post-endpoint-word">POST</a>  /config/projects/{project}/testcases/{testcase}/forms/{form} | Uploads the file with the data object of a Test Case specific configuration form. |
| | <a href="#put-config-projects-project-testcases-testcase-forms" class="put-endpoint-word">PUT</a>  /config/projects/{project}/testcases/{testcase}/forms | Updates a Test Case Preset. |
| | <a href="#put-config-projects-project-testcases-testcase-forms-form" class="put-endpoint-word">PUT</a>  /config/projects/{project}/testcases/{testcase}/forms/{form} | Updates the file with the data object of a Test Case specific configuration form. |
| <a href="#runner">**Runner**</a> | <a href="#get-runner-projects-project-testcases-testcase-run" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{testcase}/run | Runs a specific Test Case. |
| | <a href="#get-runner-projects-project-testcases-testcase-status" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{test case}/status | Retrieves the Run Status of a Test Case. | 
| | <a href="#get-runner-projects-project-testcases-testcase-stop" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{testcase}/stop  | Stops the Run task of a Test Case. |
| | <a href="#get-runner-status" class="get-endpoint-word">GET</a> /runner/status | Retrieves the status of the active and pending Test Cases. |
| | <a href="#get-runner-projects-project-testcases-testcase-options" class="get-endpoint-word">GET</a> /runner/projects/{project}/testcases/{testcase}/options | Retrieves the Run Agent configuration of a Test Case. |
| | <a href="#put-runner-projects-project-testcases-testcase-options" class="put-endpoint-word">PUT</a> /runner/projects/{project}/testcases/{testcase}/options | Updates the Run Agent configuration of a Test Case. |
| <a href="#Statistics">**Statistics**</a> | <a href="#get-statistics-projects-project-testcases-testcase" class="get-endpoint-word">GET</a> /statistics/projects/{project}/testcases/{testcase} | Retrieves the Statistics of a Test Case. |
| | <a href="#get-statistics-projects-project-testcases-testcase-config" class="get-endpoint-word">GET</a>  /statistics/projects/{project}/testcases/{testcase}/config | Retrieves the Statistics configuration of a Test Case. |
| | <a href="#put-statistics-projects-project-testcases-testcase-config" class="put-endpoint-word">PUT</a>  /statistics/projects/{project}/testcases/{testcase}/config | Updates the Statistics time configuration of a Test Case. |
| <a href="#">**Health Checks**</a> | <a href="#get-health-checks-projects-project-testcases-testcase-config" class="get-endpoint-word">GET</a>  /health-checks/projects/{project}/testcases/{testcase}/config | Retrieves the Health Checks confifgurations of a Test Case. |
| | <a href="#put-health-checks-projects-project-testcases-testcase-config" class="put-endpoint-word">PUT</a>   /health-checks/projects/{project}/testcases/{testcase}/config | Updates the Health Checks confifgurations of a Test Case. |
| <a href="#integrations">**Integrations**</a> | <a href="#get-integrations-projects-project-slack-channel-notifier" class="get-endpoint-word">GET</a>  /integrations/projects/{project}/slack/channel-notifier |  Retrieves the Integrations confifguration file of a Test Case. |
| | <a href="#put-integrations-projects-project-slack-channel-notifier" class="put-endpoint-word">PUT</a>   /integrations/projects/{project}/slack/channel-notifier | Updates the Integrations confifguration file of a Test Case. |
| <a href="#jobs">**Jobs**</a> | <a href="#post-jobs-start" class="post-endpoint-word">POST</a> /jobs/start | Starts a Project profile Job Run task. |
| | <a href="#get-jobs-trackingnumber-status" class="get-endpoint-word">GET</a> /jobs/{trackingNumber}/status | Retrieves the status of a Project profile Job. |
| | <a href="#get-jobs-trackingnumber-abort" class="get-endpoint-word">GET</a> /jobs/trackingNumber}/abort | Stops a Project profile Job Run task. |
| | <a href="#get-projects-project-jobs" class="get-endpoint-word">GET</a> /projects/{project}/jobs | Retrieves the Jobs history of a Project profile. |
| <a href="#dev">**Dev**</a>| <a href="#get-dev-version" class="get-endpoint-word">GET</a>   /dev/version | Retrieves the current version of Jeeves. |
| | <a href="#get-dev-run-agent" class="get-endpoint-word">GET</a>   /dev/run-agent | Retrieves the Run Agent details of Jeeves. |
| | <a href="#get-dev-ec2" class="get-endpoint-word">GET</a>  /dev/ec2 | Retrieves the AWS Elasctic Spot Instances. |
| | <a href="#get-dev-es" class="get-endpoint-word">GET</a>  /dev/es | Retrieves the AWS ElasticBeanstalk Instance. |
| | <a href="#get-dev-s3" class="get-endpoint-word">GET</a>  /dev/s3 | Retrieves the AWS S3 Bucket information. |
| | <a href="#get-dev-s3-project-testcase" class="get-endpoint-word">GET</a>  /dev/s3/{project}/{testcase} | Retrieves the AWS S3 Buckets Objects location. |
| | <a href="#get-dev-json_header" class="get-endpoint-word">GET</a>  /dev/json_header | Retrieves the Accepts headers. |
| | <a href="#get-dev-stop" class="get-endpoint-word">GET</a>  /dev/stop | Stops the Embeded Jetty Server of Jeeves. |
| | <a href="#post-dev-json_post" class="post-endpoint-word">POST</a>  /dev/json_post | Verifies that the Content Type is a JSON. |



# Getting Started
To start using the Jeeves API you must be conntected to the Dow Jones corporate network through GlobalProtect VPN.
To learn how to configure and connect to GlobalProtect in your computer, see the [Guide to Using the GlobalProtect VPN](https://docs.google.com/document/d/1vZSGBWDmi5Cnw8Hx1e7DLc6lRKgb321l4tsGZI2P9QQ/edit?usp=sharing).

## API Environment
To use the cURL and HTTP sample requests in your environment, change the `{API Environment URL}` parameter for one of the available environments in Jeeves. 

The following table lists the available enviroments and their URL to work with the Jeeves API: 

| Environment | Environment URL |
| ----------- | --------------- |
| localhost | http://localhost:9000/api |
| nonprod | http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/api |
| stag | http://jeeves-api-stag.us-east-1.elasticbeanstalk.com/api |

<aside class="notice"> For examples of API request in this documentation, all API endpoint calls use the <code>seed-project</code> Project profile in Jeeves, and the <code>nonprod</code> environment. 
</aside>

## Working with the API Locally
To work with the Jeeves API in your Localhost, you must configure your API Local Workspace. To configure your API Local Workspace, see the guide in the [Jeeves API Oficial Repository Documentation](https://github.dowjones.net/SharedServices/Jeeves.API/blob/master/README/api-local-config.md). 










