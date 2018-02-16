---
slug: remove-characters
redirect_from: "/article/240-remove-characters"
title: Remove Characters
---
This task will remove selected characters from a text file. This can be useful for removing unsupported characters from a file used as the input to another task.

## Settings
### Input File
_Required_  
The file to remove characters from.

### Output File
_Dependant_  
The file to output the result to (when not overwriting the input file).

### Overwrite Input File
_Required_ 
Set to true to overwrite the contents of the input file with the result, or false to write the result to the file specified in the 'Output File' property.

### Remove
_Required_  
The string or list of strings to look for in the input file, or a regular expression to match on.

### Zynk Settings
See [Common Task Settings](common-task-settings)