---
slug: switch-task
redirect_from: "/article/382-switch-task"
title: Switch Task
---
This task is used to control program flow based on the Result Code of the previous task. You can choose to execute another task based on Failure, Not Authorised, File Not Found, Success with Data and Success with No Data.

## Settings
### On Cancelled Task
_Optional_  
The task to run if the previous task returned Cancelled.

### On Fail Task
_Optional_  
The task to run if the previous task returned Fail.

### On Not Authorised Task
_Optional_  
The task to run if the previous task returned Not Authorised.

### On Not Found Task
_Optional_  
The task to run if the previous task returned Not Found.

### On Success Data Task
_Optional_  
The task to run if the previous task returned Success Data.

### On Success No Data Task
_Optional_  
The task to run if the previous task returned Success No Data.

### On Success Task
_Optional_  
The task to run if the previous task returned Success.

### Zynk Settings
See [Common Task Settings](common-task-settings)