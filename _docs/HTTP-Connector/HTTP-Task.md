---
slug: http-task
redirect_from: "/article/334-web-task"
title: HTTP Task
---
This task will perform a HTTP request of the method specified against a web server. This is used when communicating with REST, SOAP and XML-RPC based web services. Please note that the task does not support redirects, so you must enter the actual URL in the task's settings.

## Settings
### Contents Field
_Optional_  
Raw data to be submitted via a POST request can be entered here.

### Encoding Type
_Required_  
The encoding to use for requests and the response. If a charset is specified in the response headers, it will override this setting. The available encodings are UTF8, UTF7, ASCII and Unicode.

### Form Values
_Optional_  
The collection of Key-Value pairs for submitting forms to websites or where data needs to be supplied in a 'Named Value Collection'.

### Header Values
_Optional_  
The collection of Key-Value pairs containing header information where it needs to be specified. This can be used to specify Content-type or other headers such as SOAP envelope properties.

### Input
_Optional_  
The input file or data to send to the web server in the body of the request.

### Method
_Required_  
The method of the request, in most cases GET is used to fetch a page and POST is used to send information to a web server. The methods available are GET, POST, PUT, PATCH, DELETE and HEAD which are used when making REST, SOAP or XML-RPC calls.

### Output File
_Optional_  
The file to output the response returned by the web server.

### Password
_Optional_  
The password to use for HTTP basic authentication. Only required when the web server requires basic authentication.

### Retry Count
_Required_  
The number of times to retry the underlying connection if an error occurs.

### Timeout
_Required_  
The amount of time in milliseconds to wait for the web server to respond to the HTTP request. Defaults to 120000 milliseconds (2 minutes).

### URL
_Required_  
The full URL to send the HTTP request to e.g. `http://www.example.com`

### User Agent
_Optional_  
The value to use for the User-Agent header in the HTTP request. Defaults to `Zynk Software Ltd/Zynk`.

### Username
_Optional_  
The username to use for HTTP basic authentication. Only required when the web server requires basic authentication.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
### Fetching a Web page or making a REST call
1. Set the URL to [http://www.google.com](http://www.google.com/) (or any address you want to grab)
2. Set the Method to GET
3. Set the Output File to c:\google.html

### Posting data to a Web page or making a REST POST method call
1. Set the URL to [http://www.example.com](http://www.example.com/) (or any address you want to post to)
2. Set the Method to POST
3. Set the Input File to c:\data.xml where the file contains the data to be posted

You can find further examples of how to use this task in the [Website Script Based Integration](website-script-based-integration) article. 

### Troubleshooting the HTTP Task
* [Troubleshooting the HTTP Task](troubleshooting-the-http-task)