---
slug: variables
redirect_from: "/article/48-variables"
title: Variables
---
Variables are a method of storing static information that can be used within Workflows. For example you could have a Variable called "UserName" which contains the value "Paul". Variables are just "data" - they do not perform any function. The following types of variables are available in Zynk, in order of precedence:-

**System Variables**  
System variables include things such as the current date, time, year, etc. You cannot create your own or edit existing system variables, they are provided by Zynk, a list can be found in the [System Variables](using-system-variables) article.

**Global Variables**  
Global variables are defined within the main Zynk application and are accessible by all workflows and tasks. They should be used when data needs to be stored and shared between multiple workflows, an example would be the email address which Zynk should send all email notifications to. You can edit the Global variables using the 'Global Variables' button on the main toolbar, see [Using Global Variables](using-global-variables) for more information.

**Workflow Variables**  
Workflow variables are defined at the Workflow level and are accessible by all tasks within that Workflow including sub-tasks. They should be used when data needs to be stored and shared between the tasks in one workflow, examples would be a username and password or the path to a directory. You can edit the Workflow variables from the Properties tab, see [Configuring Workflow Variables](configure-workflow-variables) for more information.

**Template Variables**  
Template variables are defined within the [Razor Template](razor-template) task and are accessible from the template file. They can be used to pass information into the template at run time, such as a customer name or email address.

**Current Variables**  
Current variables are only available within [Repeater Tasks](tasks) and represent the current row of data being processed in a data set. For example, if you are using the Excel Repeater to loop through each row in an Excel spreadsheet, each row would be converted to a collection of Current variables to be used by the repeater's sub tasks e.g. "Name", "Address", "Telephone" could be the variables available. Current variables cannot be created or edited directly by the user.

## Editing Variables
All editable variables are edited within a Variable Collection Editor. A list of existing variables and their values is displayed in the 'Members' list on the left. You can change the key (i.e. name) and value of the variables using the properties list on the right. New variables can be created using the 'Add', and existing variables can be deleted using the 'Remove' button.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b094919033603f7da36fe2/file-EzuogJwrcB.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b094919033603f7da36fe2/file-EzuogJwrcB.png)

## Using Variables
See [Variables In Tasks](accessing-variables-in-tasks) for information about how to use variables in your workflow's tasks.