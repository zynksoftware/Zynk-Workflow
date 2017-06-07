---
slug: line-of-code-counter
redirect_from: "/article/200-line-of-code-counter"
title: Line of Code Counter
---
This task will count the number of source code lines within a Visual Studio solution.

## Settings
### Ignore List
_Optional_  
String array of files to be skipped.

### Root Folder
_Required_  
The root folder containing the source code to check.

### Search Pattern
_Optional_  
File search pattern for files to check e.g. \*.cs

### Difference
_Read Only_  
Number of lines changed since last time run.

### File Count
_Read Only_  
Number of files in project.

### Folder Count
_Read Only_  
Number of folders in project.

### LOC Count
_Read Only_  
Lines of Code count.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Developer Connector](developer-connector) article.