---
slug: list-files
redirect_from: "/article/238-list-files"
title: List Files
---
This task will output a list of files contained within a folder, and optionally it's sub-folders. The result can be saved to a file in XML format, or can be picked up by the next task in the workflow (by selecting the 'Output from the previous task' option in the next task's settings).

## Settings
### Folder
_Optional_  
The directory containing the files to list. Leave blank to list files in the workflow's working directory.

### Output File
_Optional_  
The XML file to save the list of files to. If left blank, the task will return a Zynk object containing the list of files. This can be used accessed by the next task in the workflow, by selecting the 'Output from the previous task' option for one of the task's settings.

### Recursive
_Required_  
Set to true if you want the task to list all files in sub-directories, or false to only list files in the directory specified.

### Search Pattern
_Optional_  
Allows you to specify the type of files to be processed. For example, `*.xml` will only list files with the .xml extension.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file, when listing files in the workflow's data directory, using the search pattern `*.xml`:

```xml
<?xml version="1.0"?>
<ArrayOfString>
  <string>C:\ProgramData\Internetware\Zynk\1.0\Data\Ebay Orders to Sage\orders_ebay.xml</string>
  <string>C:\ProgramData\Internetware\Zynk\1.0\Data\Ebay Orders to Sage\orders_zynk.xml</string>
  <string>C:\ProgramData\Internetware\Zynk\1.0\Data\Ebay Orders to Sage\orders_zynk_fail.xml</string>
  <string>C:\ProgramData\Internetware\Zynk\1.0\Data\Ebay Orders to Sage\orders_zynk_success.xml</string>
</ArrayOfString>
```