---
slug: importing-records-into-zoho-crm-v2
title: Importing Records into Zoho CRM
---
This task will import (insert or update) records into various modules in your Zoho CRM account. 

If the record in the input file contains an ID, the task will update the matching record in Zoho CRM, otherwise it will try to find a matching record to updated based on the default duplicate check field. If no match is found, a new record will be created.

The default duplicate check fields for each module are listed below.

| Module Name | Default Duplicate Check Field |
| --- | --- |
| Accounts | Account_Name |
| Campaigns | Campaign_Name |
| Cases | Subject |
| Contacts | Email |
| Deals | Deal_Name |
| Invoices | Subject |
| Leads | Email |
| PriceBooks | Price_Book_Name |
| Products | Product_Name |
| PurchaseOrders | Subject |
| Quotes | Subject |
| SalesOrders | Subject |
| Solutions | Solution_Title |
| Vendors | Vendor_Name |
| Custom Modules | Name |

## Settings
### Connection
_Required_  
The Zoho CRM Connection to use for importing records.  See the [Connecting to Zoho CRM](connecting-to-zoho-crm-v2) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed uploads to.

### Input File
_Required_  
Specify the XML file to containing the records to import. The records should be stored in the same format as the result of the [Export Records](exporting-records-from-zoho-crm-v2) task.

### Success File
_Required_  
The XML file to output successful imports to.

### Page Size
_Required_  
The number of records to upload to Zoho in each batch sent by Zynk. The maximum value is 100.

### Trigger Approvals
_Required_  
Set to true to trigger approvals after inserting or updating each record.

### Trigger Blueprints
_Required_  
Set to true to trigger blueprints after inserting or updating each record.

### Trigger Workflows
_Required_  
Set to true to trigger workflows after inserting or updating each record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, which will update the contact with ID 919325000000091003:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Records Module="contacts">
  <Record>
    <ExternalId>FRED001</ExternalId>
    <Field Name="id">919325000000091003</Field>
	<Field Name="Full_Name">Fred White</Field>
    <Field Name="Salutation">Mr</Field>
    <Field Name="First_Name">Fred</Field>
	<Field Name="Last_Name">White</Field>
    <Field Name="Email">fred.white@example.com</Field>
    <Field Name="Description" />
    <Field Name="Mailing_Street">A street</Field>
    <Field Name="Mailing_City">A city</Field>
    <Field Name="Mailing_State">A state</Field>
    <Field Name="Mailing_Country">GB</Field>
    <Field Name="Mailing_Zip">AB12CD</Field>
    <Field Name="Phone">999999999</Field>
    <Field Name="Mobile">99989989</Field>
    <Field Name="Fax">99999999</Field>
    <Field Name="Date_of_Birth">2000-01-01</Field>
    <Field Name="Email_Opt_Out">True</Field>
  </Record>
</Records>
```
