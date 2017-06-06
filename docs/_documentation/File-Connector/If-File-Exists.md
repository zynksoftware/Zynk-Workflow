---
slug: if-file-exists
redirect_from: "/article/237-if-file-exists"
title: If File Exists
---
This task will check if a file exists, and run a series of sub-tasks depending on the result. Sub-tasks can be added by dragging tasks from the Task Library and onto the If File Exists task in the workflow.

## Settings
### Equal To
_Required_  
Set to true to run the sub-tasks if the file exists, or set to false to run the sub-tasks if the file does not exist.

### Input File
_Required_  
File to check to see if it exists.

### Minimum Length
_Required_  
The minimum length the file must be in order to return True. Use -1 if file length is not relevant. This is useful when processing XML files that contain no data but still contain the XML header.

### Zynk Settings
See [Common Task Settings](common-task-settings)