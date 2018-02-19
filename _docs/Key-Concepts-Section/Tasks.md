---
slug: tasks
redirect_from: "/article/46-tasks"
title: Tasks
---
Tasks are individual actions that are linked together to form a Workflow. There are several type of tasks available when creating a Workflow in Zynk:

**Task**  
A simple one-shot or "atomic" action that usually accepts an input and provides an output. The majority of simple tasks do not rely on any other tasks. An example of this would be the "Copy File" task which copies a file from one location to another. Simple Tasks can be chained together to achieve more complex functionality such as Downloading a Page from a Website, Converting To PDF, Sending PDF via Email. There are also accounting tasks to automate complex business processes such as importing Customers and Sales orders from an XML data feed.

**Repeater Task**  
A task that loops through a data set and runs a collection of sub-tasks for each record in that data set. An example of this would be an [Excel Repeater](excel-repeater-task) which contains a list of email addresses and for each email address you want to create a customised report such as a Statement and then Email that statement to each customer.

**Conditional Tasks**  
These are special tasks such as If, Switch and Else, these tasks are used to control the workflow and branch depending on the condition of the previous tasks. For example you could check if a file exists then perform one action or if it does not exist, perform an alternative action.

**Container Task**  
This is simply a task that acts as a container for other tasks and does nothing other than allow you to logically group tasks so that the workflow is more visually appealing, more information can be found in the [Container Task](container-task) article.

**Sub-Task**  
A sub-task is a normal task that is called as part of a Repeater, Conditional or Container Task.

**Render Task**  
The Render Task allows you to create documents, CSV, XML, HTML or any other output file from a data set or variable using a powerful templating language. For example you may want to export customer invoices from your accounting system, render an invoice and send that via email automatically. Zynk uses the Razor templating engine to perform Render Tasks, more information can be found on our [Razor Template](razor-template) article.

You can find information about how to use tasks in [Working With Tasks](working-with-tasks).

## Common Task Settings
All Tasks contain a number of settings. Every Task within Zynk has a set of *common* settings, in addition to the any settings which are specific to that particular task. For instance, all tasks in Zynk have an 'Enabled' setting, which determines whether the each task should run when running the workflow, whereas the 'Attachments' setting is unique to the Send Email task.

We have an article about [Common Task Settings](common-task-settings) common across all tasks.

## Task Result Codes
Each time a task runs, the Last Result setting will be updated to show the result code that was returned by the task. The different result codes are listed below:

 * **Success** - The task executed successfully
 * **Success No Data** - The task executed successfully but no data was returned
 * **Fail** - The task failed, refer to the log for further information
 * **Not Found** - The task failed because the input could not be found
 * **Not Authorised** - The task failed due to a permissions or authorisation error
 * **Cancelled** - The task was cancelled by the user
 * **Unknown** - An unknown error occurred, refer to log for more information. This is can be caused by the Zynk.exe process being terminated.

You can use Result codes to launch another task depending on the result of the last task, by using the [Switch Task](switch-task).
