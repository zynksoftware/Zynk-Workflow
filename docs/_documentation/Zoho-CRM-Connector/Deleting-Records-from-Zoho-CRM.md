---
slug: deleting-records-from-zoho-crm
redirect_from: "/article/363-deleting-records-from-zoho-crm"
title: Deleting Records from Zoho CRM
---
This task will delete a record from your Zoho CRM account.

## Settings
### Connection
_Required_  
The Zoho CRM Connection to use for deleting records.  See the [Connecting to Zoho CRM](connecting-to-zoho-crm) article if you require more information on how to create/manage connections.

### Input File
_Required_  
The file containing the record(s) that you want to delete. The data should be in the same format as the output from [Downloading Records from Zoho CRM](downloading-records-from-zoho-crm). The only required field is the ID.

### Record Type
_Required_  
The type of record to be deleted. The available options are:	

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

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, which will delete the account with ID 919325000000064034:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Accounts>
    <row no="1">
        <FL val="ACCOUNTID">919325000000064034</FL>
    </row>
</Accounts>
```