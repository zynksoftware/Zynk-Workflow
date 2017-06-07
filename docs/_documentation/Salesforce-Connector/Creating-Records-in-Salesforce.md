---
slug: creating-records-in-salesforce
redirect_from: "/article/290-creating-records-in-salesforce"
title: Creating Records in Salesforce
---


This task will create a single new record in the Salesforce system and return the response data in XML format. If you have multiple records to create, you can use this task as a sub-task of an [XML Repeater](xml-repeater) task, or use the [Bulk Salesforce Operation](bulk-salesforce-operation) task instead.


## Settings

### Connection 
_Required_  
The Salesforce connection to use, see [Connecting to Salesforce](connecting-to-salesforce)

### Input File
_Required_  
The XML file containing the record to be created in Salesforce. XML node names must match the Salesforce API field names. Custom fields are supported, and are usually named like `Account_Ref__c`. Values must be provided for required fields that do not have a preconfigured default value, but all other fields don't require a value. If no value is provided for a field and it has a default value configured, the default value will be used, otherwise it will be set to null. Note that the `Id`, `CreatedDate`, `CreatedById`, `LastModifiedDate`, `LastModifiedById`, and `SystemModstamp` fields cannot be set by the task.

### Object Type
_Required_  
The name of the object to create e.g. Account

### Output File
_Required_  
The file to save the response from Salesforce to. If a record was created successfully, the response will contain its ID. If the record was not created, the response will contain an error message detailing what went wrong.

## Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample input file, which will create an account with the name "Internetware Limited" and set the `Balance__c` custom field to 150.00:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<root>
  <Name>Internetware Limited</Name>
  <Balance__c>150.00</Balance__c>
</root>
```

Sample output file:

```json
{
    "id": "00140000011r9OrAAI",
    "success": true,
    "errors": []
}
```