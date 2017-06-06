---
slug: if-input-contains
redirect_from: "/article/373-if-input-contains"
title: If Input Contains
---
This task will check whether an input contains some specified value, and run a series of sub-tasks depending on the result. Sub-tasks can be added by dragging tasks from the Task Library and onto the If Input Contains task in the workflow.

## Settings
### Equal To
_Required_  
Set to true to run the sub-tasks if the input contains the match value, or set to false to run the sub-tasks if the input does not contain the match value.

### Input
_Required_  
The input value to check. For instance, this could be set to a workflow variable, a Razor script or the content of a file.

### Match
_Required_  
The value the input should contain.

### Zynk Settings
See [Common Task Settings](common-task-settings)