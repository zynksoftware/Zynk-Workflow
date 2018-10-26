---
slug: if-truth-record-exists
redirect_from: "/article/718-if-truth-record-exists"
title: If Truth Record Exists
---
This task will check whether a record exists in Zynk's truth table, and run a series of sub-tasks depending on the result.

For more detailed information on the truth table please visit the [Truth Database](truth-database) page.

## Settings
### Equal To
_Required_  
Set to true to run the sub-tasks if a matching truth record is found, or false to run the sub-tasks if no matching truth record is found.	  

### Match Truth Records On
_Required_
The list of criteria to use to find the truth record. Only truth records which match all of the criteria will be matched. Each criteria added to the list has the following settings:	

 * Match Type - Select the type of check to perform on the value of the field.
 * Name - Select the field name to check.
 * Value - Enter the value to check for.

### Zynk Settings
See [Common Task Settings](common-task-settings)