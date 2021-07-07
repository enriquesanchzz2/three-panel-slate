# Watson API Reference Documentation

Watson is a monitor tool that helps developers analyze a project’s web performance. With Watson, you can do the following:

  * Design Test Cases to validate service availability and throughput.
  * Group load Test Cases by Project profiles.
  * Run, stop, and reconfigure Test Cases to validate service availability.
  * Monitor a website performance through different Test Cases.
  * Obtain detailed reports with graphics about their website performance.
  

This documentation guides you through the resources, methods, and endpoints of the Watson API. It also contains examples of request bodies and responses, so that you can start working with the Watson API as smoothly as possible.


The following table contains the resources available in the Watson API:

| API Resource | Endpoint | Endpoint Description |
| ------------ | -------- | -------------------- |
| <a href="#projects"> **Projects**</a> | <a href="#get-projects" class="get-endpoint-word">GET</a> /projects | Retrieves the data objects of the Project profiles available in Watson. |
| | <a href="#post-projects" class="post-endpoint-word">POST</a> /projects | Creates a new Project profile. |
| | <a href="#put-projects-project" class="put-endpoint-word">PUT</a> /projects/{project} | Updates the data object of a Project profile. |
| | <a href="#delete-projects-project" class="delete-endpoint-word">DELETE</a> /projects/{project} | Deletes a Project profile. |



# Getting Started
To start using the Watson API you must be conntected to the Good Corp. corporate network through GlobalProtect VPN.
To learn how to configure and connect to GlobalProtect in your computer, see the [Guide to Using the GlobalProtect VPN](#).

## API Environment
To use the cURL and HTTP sample requests in your environment, change the `{API Environment URL}` parameter for one of the available environments in Watson. 

The following table lists the available enviroments and their URL to work with the Watson API: 

| Environment | Environment URL |
| ----------- | --------------- |
| localhost | http://localhost:9000/api |
| nonprod | http://watson-nonprod.com/api |
| stag | http://watson-stag.com/api |

<aside class="notice"> For examples of API request in this documentation, all API endpoint calls use the <code>seed-project</code> Project profile in Watson, and the <code>nonprod</code> environment. 
</aside>

## Working with the API Locally
To work with the Watson API in your Localhost, you must configure your API Local Workspace. To configure your API Local Workspace, see the guide in the [Watson API Oficial Repository Documentation](#). 










