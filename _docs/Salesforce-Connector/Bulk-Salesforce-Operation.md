---
slug: bulk-salesforce-operation
redirect_from: "/article/289-bulk-salesforce-operation"
title: Bulk Salesforce Operation
---


This task will update, insert or delete multiple records in Salesforce at a time. The records can all be stored in a single file, or split up into separate files.


## Settings
### Connection
_Required_  
The Salesforce Connection to use for the bulk operation. See the [Connecting to Salesforce (Bulk)](connecting-to-salesforce-bulk) article if you require more information on how to create/manage connections.

### Content Type
_Optional_  
Select the type of content being uploaded to Salesforce. The available options are XML and CSV.

### External ID
_Dependant_  
The field in Salesforce of type External ID to use to when looking for existing records. Required when the Operation Type is set to Upsert. If no External ID field is available, the [Importing Records to Salesforce (Bulk)](importing-records-to-salesforce-bulk) task can be used as an alternative.

### Input File(s)
_Required_  
The file(s) to upload to Salesforce. XML field names must match Salesforce API field names, custom fields are usually named like "Account_Ref__c". If using multiple files, you can either select the 'Use a list' option and enter each file name, or select the 'Use output from the previous task' option and generate a list of files dynamically using a  [List Files](list-files) task.

### Object Type
_Required_  
The record type to upload e.g. Account.

### Operation Type
_Required_  
Select the type of operation to perform against Salesforce. Choose from delete, insert, upsert, update or hard delete.

### Output Location
_Required_  
The file or folder to output the results of the operation to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples

Sample input file, which when the Operation Type is set to Update, will update the accounts with ID 0014000000LALdXXXX and 0012300000LALdXXXY, setting values for the credit limit and balance custom fields:
```xml
<?xml version="1.0" encoding="utf-8"?>
<sObjects xmlns="http://www.force.com/2009/06/asyncapi/dataload">
  <sObject>
    <Id>0014000000LALdXXXX</Id>
    <Balance__c>250.00</Balance__c>
    <Credit_Limit__c>1000.00</Credit_Limit__c>
  </sObject>
  <sObject>
    <Id>0012300000LALdXXXY</Id>
    <Balance__c>5230.00</Balance__c>
    <Credit_Limit__c>6000.00</Credit_Limit__c>
  </sObject>
</sObjects>
```

Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<sObjects xmlns="http://www.force.com/2009/06/asyncapi/dataload">
  <sObject>
    <Id>0014000000LALdXXXX</Id>
    <Balance__c>250.00</Balance__c>
    <Credit_Limit__c>1000.00</Credit_Limit__c>
  </sObject>
  <sObject>
    <Id>0012300000LALdXXXY</Id>
    <Balance__c>5230.00</Balance__c>
    <Credit_Limit__c>6000.00</Credit_Limit__c>
  </sObject>
</sObjects>
```
