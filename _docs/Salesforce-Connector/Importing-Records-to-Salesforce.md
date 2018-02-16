---
slug: importing-records-to-salesforce
redirect_from: "/article/295-uploading-records-to-salesforce"
title: Importing Records to Salesforce
---
This task will update existing records or insert new records, based on whether the record already exists in Salesforce. Existing records are found based on a particular field of type External Id, as specified in the task's settings. If there is no External Id field to use lookup existing records for the given object type, you can use the [Importing Records to Salesforce (Bulk)](importing-records-to-salesforce-bulk) task as an alternative. This task will only upsert a single record, if you have multiple records to upsert, you can use this task as a sub-task of an [XML Repeater](xml-repeater) task, or use the [Bulk Salesforce Operation](bulk-salesforce-operation) task instead.

## Settings
### Connection 
_Required_  
The Salesforce connection to use, see [Connecting to Salesforce](connecting-to-salesforce)

### Input File
_Required_  
The XML file containing the data to be inserted or updated. XML node names must match the Salesforce API field names. Custom fields are supported, are usually named like `Account_Ref__c`.

### Key Field
_Required_  
The lookup field to used for existing records. Note this must be a custom field in Salesforce and marked as an External Id. e.g. `Account_ref__c`

### Key Value
_Required_  
The value to lookup in the key field. This field supports variables and scripting. e.g. ABC001

### Object Type
_Required_  
The name of the object to create e.g. Account

### Output File
_Required_  
The file to save the response from Salesforce to.

### Zynk Settings 
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, which will update the Name field and `Balance__c` custom field on the Account in Salesforce with `Account_Ref__c = "INT001"`:

```xml
<root> 
  <Account_Ref__c>INT001</Account_Ref__c>
  <Name>Internetware Limited</Name>    
  <Balance__c>150.00</Balance__c>
</root>
```