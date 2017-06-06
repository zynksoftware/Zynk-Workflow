---
slug: find-and-replace-text
redirect_from: "/article/236-find-and-replace-text"
title: Find and Replace Text
---
This task will run a find and replace on the contents of a text file.

## Settings
### Input File
_Required_  
The file to find and replace text in.

### Output File
_Dependant_  
The file to output the result to (when not overwriting the input file).

### Overwrite Input File
_Required_  
Set to true to overwrite the contents of the input file with the result of the find and replace, or false to write the result to the file specified in the 'Output File' property.

### Find
_Required_  
The string or list of strings to look for in the input file, or a regular expression to match on.

### Replace
_Required_  
The string to replace all matches with.

### Zynk Settings
See [Common Task Settings](common-task-settings)