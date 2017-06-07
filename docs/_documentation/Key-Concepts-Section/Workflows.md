---
slug: workflows
redirect_from: "/article/45-workflows"
title: Workflows
---
In Zynk a Workflow is a collection of Tasks or "actions", that when ran together can be used to automate your business processes.  Once configured a workflow can either be ran on demand through Zynk, or setup using Windows Schedule Tasks to run on regular basis.  Each workflow can consist of up to 20 tasks, so some processes may need to be split up over multiple workflows.

For information on how to create workflows using Zynk, see [Creating New Workflows](creating-new-workflows)

## Tasks
You build up the structure of the workflow by adding tasks from the Task Library, these are added to the current workflows Task List.  The example below shows an example workflow that could be used to download orders from a website, convert the data into the required format, import the data as invoices in Sage, and finally email the customers their invoice.  You can edit the settings for each task using the grid on the right of Zynk.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b08f7c9033603f7da36fb3/file-1uwzUl6pIN.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b08f7c9033603f7da36fb3/file-1uwzUl6pIN.png)

## Properties
Each workflow has a set of properties which can be configured on the 'Properties' tab.

### Email Workflow Report
_Required_  
Zynk can email a workflow report after running, which details the tasks that ran and any messages logged.  The options available are:-	  

 * Never (default) - will never send any report emails
 * Always - will always send a report regardless if the workflow was successful or not
 * OnFailure - will only send a report if one of the tasks fails (and break of fail for that task is true)
 * OnErrorFlag - will only send a report if the Set Error Flag has been used in the workflow, allowing for finer control of error handling

### Email Workflow Report To
_Optional_  
The email address(es) to send the workflow reports to.

### Include Workflow Log
_Required_  
Choose when the log messages should be included in the report.

### Description
_Optional_  
You can enter a brief description of the workflow's functions here.

### Documentation
_Optional_  
You can enter HTML formatted documentation of the workflow's functions here.

### History House Keeping
_Required_  
Settings to control how long entries in the workflow history should be kept. The default setting is 90 days.

### Id
_Read Only_  
The workflow's unique identification number.

### Last Ran
_Required_  
The date the workflow was last ran.

### Last Result
_Required_  
The result when the workflow was last ran.

### Name
_Read Only_  
The name of the workflow. To rename a workflow, right click on the workflow in the 'My Workflows' tab, and click 'Rename'.

### Show Help On Startup
_Required_  
Set to true to display the documentation when the workflow is opened.

### Use Mutex
_Required_  
Set to true to prevent more than one copy of the workflow running simultaneously.

### Variables
_Required_  
The list of workflow variables. See [Variables](variables) for more information.

### Version
_Read Only_  
The version of Zynk which last saved the workflow.

## Typical Use Cases
Two of the most common use cases for workflows are to download data from an e-commerce website and import in into Sage, or export data from Sage and upload it to an e-commerce website. See below for an overview of how this can be achieved.

### Download from website to Sage

 * Download the required data from the website using the appropriate task. For example, this may be the [Amazon Order Download](downloading-orders-from-amazon-marketplace) task or the [Magento Order Download](downloading-orders-from-magento) task.
 * Transform the data to the Zynk format. This can be done using the [Auto Mapper](auto-mapper) task or an [XSLT Transform](xslt-transform).
 * Import the data into Sage using the appropriate task. For example, this may be the [Sage 50 Import Sales Orders](importing-sales-orders-into-sage-50-uk) task. 

### Upload from Sage to website

 * Export the required data from Sage using the appropriate task. For example, this may be the [Sage 50 Export Stock Records](exporting-stock-records-from-sage-50-uk) task.
 * Transform the data to the website's format. This can be done using the [Auto Mapper](auto-mapper) task or an [XSLT Transform](xslt-transform).
 * Upload the data to the website using the appropriate task. For example, this may be the [Magento Upload Inventory](uploading-inventory-to-magento) task.

