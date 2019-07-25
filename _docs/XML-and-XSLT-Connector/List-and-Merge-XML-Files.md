---
slug: list-and-merge-xml-files
title: Converting XML to CSV
---
The List and Merge XML Files task will allow you to list xml files from a folder (and optionally sub folders) into a single XML file. 

Please note, the file extension of your XML files must be '.xml' as the task will append your search pattern with this file extension if it is not in the setting value.

## Settings
### Folder 
_Required_
"The folder you want to list. The default value will be your working directory ('.').

### Output File
_Required_
The file to save XML records to. The XML files listed in the previous setting will be merged into this single output file.

### Recursive
_Required_
If the search should recurse into sub folders. This is set to false by default.

### Search Pattern
_Required_
The search to use when listing files e.g. *.xml for only XML files. If you do not end your search pattern with '.xml' then the task will append the file extension to your search pattern. 

### Zynk Settings
See [Common Task Settings](common-task-settings)