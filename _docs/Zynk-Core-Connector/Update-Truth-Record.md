---
slug: update-truth-record
redirect_from: "/article/720-update-truth-record"
title: Update Truth Record
---
This task will check whether a record exists in Zynk's truth table, and update it if it does, otherwise it will insert a new truth record.

For more detailed information on the truth table please visit the [Truth Database](truth-database) page.

## Settings
### Match Truth Records On
_Required_  
The list of criteria to use to find the existing truth record. Only truth records which match all of the criteria will be matched. Each criteria added to the list has the following settings:	

 * Match Type - Select the type of check to perform on the value of the field.
 * Name - Select the field name to check.
 * Value - Enter the value to check for.

### Update Fields
_Required_  
The list of field values to insert/update in the truth table. Each field added to the list has the following settings:	

 * Name - Select the field name to insert/update the value into.
 * Value - Enter the value to insert/update the field to.

### Zynk Settings
See [Common Task Settings](common-task-settings)