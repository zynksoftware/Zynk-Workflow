---
slug: inserting-records-to-sugarcrm
redirect_from: "/article/327-uploading-records-to-sugarcrm"
title: Inserting Records to SugarCRM
---


This task will insert a new record or update an existing record in Sugar CRM. An update is performed if the record ID was provided in the input file, or an existing record is found in Sugar where the value of the key field matches the value specified in the input file. If no matching record is found, a new record will be created in Sugar.



The task supports setting relationships to existing records in Sugar, using the [link field](link-fields) name. The record to link to must already exist in Sugar, the task will not create it if it does not exist. Any field can be used to look up the related record in Sugar, such as the ID or Name, and the task will use the first matching record found.


## Settings

### Connection 
_Required_  
The SugarCRM Connection to use for querying records. See [Connecting to SugarCRM](connecting-to-sugarcrm).

### Fail File
_Required_  
The file to save failed records to.

### Input File
_Required_  
The file containing records you'd like to import.

### Success File
_Required_  
The file to save successful records to.

### Key Field(s)
_Required_  
The field(s) to use when looking for a matching existing record in Sugar. Defaults to the ID field if not specified.

### Module Name
_Required_  
The name of the module to insert records to e.g. Opportunity. Note that the module name is case sensitive.

### Operation Type
_Required_  
Select the type of operation to perform against Sugar. The available options are:  

- Upsert - The task will update records if they already exist, or create them if they do not.
- Insert - The task will only create new records. If an existing record is provided in the input file, it won't be updated in Sugar.
- Update - The task will only update existing records. If a new record is provided in the input file, it won't be created in Sugar.

### XPath
_Required_
Specify the XPath query to use to obtain the records from the input file. This property defaults to Rows/Row but allows you to specify another XPath query for the records.

## Zynk Settings 
See [Common Task Settings](common-task-settings)


## Examples


You can find an example of how to use this task in the [Sugar CRM to Sage 50 Integration](sugar-crm-to-sage-50-integration) article.



The sample input file shown below will create a new account called "Zynk Software Ltd", and update the existing account with ID 52828444-a7fc-4ecc-72f8-51a48143b6ed. Note that the XPath Query setting would need to be set to  `Rows/Row` to access the records contained in this file.


```xml
<?xml version="1.0" encoding="utf-8"?>
<Rows>
  <Row name="Zynk Software Ltd" phone_office="123456789" />
  <Row id="52828444-a7fc-4ecc-72f8-51a48143b6ed" name="Internetware Ltd" phone_office="123456789" />
</Rows>
```


A sample success file is shown below, containing the ID of the newly created account.


```xml
<?xml version="1.0" encoding="utf-8"?>
<Rows>
  <Row id="cbef463d-13ed-4a25-ae54-828985fa37a2" name="Zynk Software Ltd" phone_office="123456789" />
  <Row id="52828444-a7fc-4ecc-72f8-51a48143b6ed" name="Internetware Ltd" phone_office="123456789" />
</Rows>
```


The sample input file shown below shows the creation of an opportunity with a related account. In this case the [link field](link-fields) "accounts" is set to the account with ID 5f87cba4-a90e-3b2a-57ab-5305f2776fea. Note that the XPath Query setting would need to be set to `Opportunities/Opportunity` to access the records contained in this file.


```xml
<?xml version="1.0" encoding="utf-8"?>
<Opportunities>
  <Opportunity name="Zynk Software" date_closed="2014-09-25" sales_stage="Closed Won" amount="175" description="New printer">
	<accounts>
	  <id>5f87cba4-a90e-3b2a-57ab-5305f2776fea</id>
	</accounts>
  </Opportunity>
</Opportunities>
```
