---
slug: common-task-settings
redirect_from: "/article/57-zynk-settings"
title: Common Task Settings
---
The following settings are common across all tasks in Zynk.

## Settings
### Break on Failure
_Required_  
If set to True the workflow will stop running if the task does not end successfully, otherwise the workflow will continue.

### Enabled
_Required_  
Set to True to run this task when the workflow is executed, otherwise it will be skipped. If a container task is not enabled none of the child tasks will be ran.

### Last Ran
_Optional_  
The date the task was last ran.

### Last Result
_Required_  
The end result of when the task was last ran.

### On Failure Task
_Optional_  
An optional task to run if the task is unable to complete successfully.

### Task Name
_Required_  
The name of the task within the workflow, it can be helpful if you have more than one of the same task.

### Task Type
_Read Only_  
The type code of the task, this cannot be modified.

### Unique ID
_Read Only_  
The unique identifier of the task, this cannot be modified.