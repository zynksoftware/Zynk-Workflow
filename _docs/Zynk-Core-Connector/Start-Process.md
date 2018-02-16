---
slug: start-process
redirect_from: "/article/379-start-process"
title: Start Process
---
The start process task will execute any external program or application. Specify the Input as the name of the file you are looking to execute e.g. `Reader.exe`, any Arguments such as a filename or flags if you want to print a file. You can have the Workflow wait for the process to complete or specify a period in milliseconds before continuing execution of the Workflow.

## Settings
### Arguments
_Optional_  
Any additional arguments to be passed after the program name e.g. `myfile.txt /p`

### Input
_Required_  
The name of the process to be started e.g. `Notepad.exe`

### Print
_Required_  
Set to true if Zynk should print the given document. Defaults to False.

### Time Out
_Required_  
Only used when Wait For Process is set to true. The time out allows you to specify how long the Workflow should wait (in milliseconds) before continuing execution. Defaults to 5000.

### Wait For Process
_Required_  
Set to true if Zynk should wait for the process to complete. Defaults to False.

### Zynk Settings
See [Common Task Settings](common-task-settings)