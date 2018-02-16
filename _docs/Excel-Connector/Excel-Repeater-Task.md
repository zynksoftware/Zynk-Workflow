---
slug: excel-repeater-task
redirect_from: "/article/228-excel-repeater-task"
title: Excel Repeater Task
---
This task will loop or iterate through the rows of an Excel worksheet, running the sub-tasks contained within this task for each row that is processed.  
To add sub-tasks, drag and drop tasks from the task library onto this task. The sub-tasks are displayed as child nodes of the Excel Repeater task.

This task is typically used with a Razor template to create documents, Emails or SMS messaging.

## Settings
### Include Headers
_Required_  
Set this to true if the first row of the Excel worksheet contains column names, not data.  Defaulted to true.

### Input File
_Required_  
The absolute or relative file path on the local computer or network to the Excel file you would like to repeat/loop over.  See the [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works.  Defaulted to 'Output from the previous task'.	  

### Worksheet Name
_Required_  
The name of the worksheet in the Excel file that you would like to process.  No Default.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
For every record in the selected Worksheet of the Excel Input File, the columns are available to each sub-task as a current variable. If the Include Headers setting is set to true, the variable names will correspond to the values in the first row of the Input File. Otherwise, the variables will be named based on the column's index and preceded by the letter F e.g. F1, F2, F3 etc.

The sub-tasks can access the values of the variables using razor, so they can be used in templates, or within task settings that support [Zynk Objects](zynk-objects). For example  `@(Context.Current["F1"])` would be used to access the first value in a row when Include Headers is set to false.

See [Accessing Variables in Tasks](accessing-variables-in-tasks) for more information on using context variables.