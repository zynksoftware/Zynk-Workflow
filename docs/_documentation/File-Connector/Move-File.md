---
slug: move-file
redirect_from: "/article/239-move-file"
title: Move File
---
This task will move a file from one location to another.

## Settings
### Input File
_Required_  
The name of file to be moved.

### Output File
_Required_  
The location to move the file to.

### Overwrite File
_Required_  
Set to True to overwrite the Output File if it exists, or set to False to not move the file if it already exists. Defaults to True.

### Prepend Timestamp
_Required_  
Adds a timestamp to start of file name. e.g. `20010214120000\_filename.xml`

### Timestamp Format
_Required_  
Format for timestamp - Uses yyyyMMddHHmmssffff by default for millisecond based timing.

### Zynk Settings
See [Common Task Settings](common-task-settings)