---
slug: if-email-exists
redirect_from: "/article/226-if-email-exists"
title: If Email Exists
---
This task will check whether an email address exists, and run a series of sub-tasks depending on the result. Sub-tasks can be added by dragging tasks from the Task Library and onto the If Email Exists task in the workflow.

## Settings
### Equal To
_Required_  
Set to True to run the sub-tasks if the email address exists, or set to false to run the sub-tasks if the email address does not exist.

### Email Address To Contact SMTP Server As
_Optional_  
When the option 'Validate Against SMTP Server' is enabled, you must provide an email address to connect to the target SMTP server.

### Email Address To Validate
_Required_  
The email address or list of email addresses to be checked.

### Strong Validation
_Required_  
Set to true to make the existence check return true only when the email address can be validated against the destination SMTP server.

### Validate Against SMTP Server
_Required_  
Set to True to validate the address against the SMTP server, or set to false to only check that the format of the email address is valid.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
An article on the use of this task is available [here](using-email-connector).