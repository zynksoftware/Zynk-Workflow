---
slug: using-developer-connector
redirect_from: "/article/647-using-developer-connector"
title: Using Developer Connector
---
This article will give an overview of how the tasks in the Developer connector can be used within a workflow, for example to automate the build process for Visual Studio projects, or to perform automated tests against your website.

## Build Project
The Build Project task can be used to build a single project created in Visual Studio.

As an example we will build a project from the `SampleApp.SampleProject.csproj` file using the following settings:

### Project File
The path to SampleApp.SampleProject.csproj

The result of the task will be that the SampleApp.SampleProject.csproj project is built to a dll file. 

## Build Solution
The Build Project task can be used to build a solution created in Visual Studio. 
As an example we will build a solution from the `SampleApp.sln` file using the following settings:

### Solution File
The path to SampleApp.sln

## Line Of Code Counter Example
The Line Of Code Counter task can be used to count the lines of code in a solution created in Visual Studio. 
As an example we will count the lines of code in the SampleApp solution using the following settings:

### Ignore List
Leave empty to count the code in all files 

### Root Folder 
The path to the root folder of the SampleApp solution

### Search Pattern 
*.cs 

## Link Checker Example
The Link Checker task can be used to check a web page for broken links.As an example we will check the links on the home page of zynk.com using the following settings: 

### Depth 
1

### Output File 
link_check_results.xml 

### Timeout 
100000 

### URL 
http://zynk.com/

The results of the task will be saved to the link_check_results.xml file. 

## Ping Host Example
The Ping Host task can be used to send a ping to a web server to check if it is responding. It is a condition task, so you can add sub-tasks to it which will run depending on what the result of the ping was. For example you could use the send email task to send an email notification if a website has gone down.  As an example we will ping zynk.com and run the sub-tasks if the ping fails using the following settings:

### Equal To
False 

### Host
http://zynk.com/

### Timeout
5000

## Validate Resource Example
The Validate Resource task can be used to check the markup validity of a web document.As an example we will validate the zynk.com home page using the following settings: 

### Output File
validation_result.html 

### URL 
http://zynk.com/

### Validation URL
http://validator.w3.org/check 

The results of the task will be saved to the validation_result.html file.