---
slug: uploading-records-to-zoho-crm
redirect_from: "/article/365-uploading-records-to-zoho-crm"
title: Uploading Records to Zoho CRM
---
This task will upsert (insert or update) various types of records to your Zoho CRM account. If the record in the input file contains an ID, the task will update the matching record in Zoho CRM, otherwise it will insert a new record.

## Settings
### Connection
_Required_  
The Zoho CRM Connection to use for deleting records.  See the [Connecting to Zoho CRM](connecting-to-zoho-crm) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed uploads to.

### Input File
_Required_  
Specify the XML file to containing the records to upload. The records should be stored in the same format as the result of the 'Download Records' task.

### Success File
_Required_  
The XML file to output successful uploads to.

### Module Name
_Required_  
The type of record to be uploaded. The available options are:	

 * Accounts
 * Calls
 * Campaigns
 * Contacts
 * Events
 * Invoices
 * Leads
 * Potentials
 * Price Books
 * Products
 * Purchase Orders
 * Quotes
 * Sales Orders
 * Solutions
 * Tasks
 * Vendors

### Trigger Workflow Rules
_Required_  
Set to true to trigger workflows after inserting or updating a record in Zoho CRM.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, which will update the contact with ID 639175000000068003, and create a new contact:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Contacts>
    <row no="1">
        <FL val="CONTACTID">639175000000068003</FL>
        <FL val="First Name">Scott</FL>
        <FL val="Last Name">James</FL>
        <FL val="Email">test2@test.com</FL>
        <FL val="Phone">999999999</FL>
        <FL val="Fax">99999999</FL>
        <FL val="Mobile">99989989</FL>
        <FL val="Assistant">John</FL>
    </row>
    <row no="2">
        <FL val="First Name">John</FL>
        <FL val="Last Name">Smith</FL>
        <FL val="Email">john@example.com</FL>
        <FL val="Phone">123456789</FL>
        <FL val="Fax">123456789</FL>
        <FL val="Mobile">123456789</FL>
        <FL val="Assistant">Bill</FL>
    </row>
</Contacts>
```
