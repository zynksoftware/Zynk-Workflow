---
slug: file-repeater
redirect_from: "/article/235-file-repeater"
title: File Repeater
---
The file repeater will loop through a directory of files and process a number of sub-tasks for each file in the directory.

## Settings
### Modified Since
_Required_  
The date to use when looping through modified files only. This will update automatically each time the task runs.

### Only Modified Files
_Required_  
Set to True to only loop over files created or modified since the date shown in the Modified Since setting. Set to False to loop over every file. Defaults to False.

### Recursive
_Required_  
Set to True to loop through all files in sub folders, False will only loop through files in the top level folder. Defaults to False.

### Input Directory
_Required_  
Directory to process or loop through.

### Search Pattern
_Optional_  
Allows you to specify the type of files to be processed e.g. `*.csv`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
The following variables are available to the sub-tasks. To use these variables, reference them in templates as `@Context.Current["FullName"]`, or within the task settings using the Razor option.

 * CreationTime
 * Directory
 * DirectoryName
 * Extension
 * FullName
 * LastAccessTime
 * LastWriteTime
 * Length
 * Name
 * NameWithoutExtension