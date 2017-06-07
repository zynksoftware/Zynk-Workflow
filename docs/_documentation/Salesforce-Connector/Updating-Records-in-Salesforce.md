---
slug: updating-records-in-salesforce
redirect_from: "/article/294-updating-records-in-salesforce"
title: Updating Records in Salesforce
---
This task will update an existing record or existing fields on a record, and requires the Salesforce record ID to update the record. It will only update a single record, if you have multiple records to update, you can use this task as a sub-task of an [XML Repeater](xml-repeater) task, or use the [Bulk Salesforce Operation](bulk-salesforce-operation) task instead.

## Settings

### Connection 
_Required_  
The Salesforce connection to use, see [Connecting to Salesforce](connecting-to-salesforce)

### Input File
_Required_  
The XML file containing the data to be updated. XML node names must match the Salesforce API field names. Custom fields are supported, and are usually named like `Account_Ref__`. Values can only be provided for fields which are updateable. Note that the `Id`, `CreatedDate`, and `CreatedById` fields cannot be set by the task. The `LastModifiedDate`, `LastModifiedById`, and `SystemModstamp` fields will be updated automatically.

### Object Id
_Required_  
The ID of the object to be updated e.g. 0015000000VALDtAAP

### Object Type
_Required_  
The name of the object to create e.g. Account

### Output File
_Required_  
The file to save the response from Salesforce to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Salesforce to Sage 50 Integration](salesforce-to-sage-50-integration) article.

Sample input file, which will update the `Name` field and `Balance__c` custom field on a record in Salesforce:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<root>
  <Name>Internetware Limited</Name>
  <Balance__c>150.00</Balance__c>
</root>
```