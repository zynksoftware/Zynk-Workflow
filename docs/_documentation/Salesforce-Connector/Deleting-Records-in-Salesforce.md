---
slug: deleting-records-in-salesforce
redirect_from: "/article/291-deleting-records-in-salesforce"
title: Deleting Records in Salesforce
---


This task will execute a Delete call against a specific Salesforce Record. It will delete all child data associated with a record, for example deleting an Account will remove all the Opportunities, Contacts etc. related to that Account. Deleted records can be undeleted by your Salesforce Administrator, but there is no function within Zynk to undelete a record. This task will only delete a single record, if you have multiple records to delete, you can use this task as a sub-task of an [XML Repeater](xml-repeater) task, or use the [Bulk Salesforce Operation](bulk-salesforce-operation) task instead.


## Settings

### Connection 
_Required_  
The Salesforce connection to use, see [Connecting to Salesforce](connecting-to-salesforce)

### Object Type
_Required_  
The name of the object to create e.g. `Account`

### Object Id
_Required_  
The identifier for the object to be deleted. E.g `TEST1234`

### Output File
_Required_  
The file to save the response from Salesforce to.

### Zynk Settings 
See [Common Task Settings](common-task-settings)
