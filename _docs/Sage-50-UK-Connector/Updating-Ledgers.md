---
slug: updating-ledgers
redirect_from: "/article/755-update-ledgers"
title: Updating Ledgers
---
This task will automatically post invoices within Sage 50. This will create the relevant transactions against the customer account for the invoice and update the customer's balance.

This task can only be used with Sage 50 v21 (2015) and above. Older versions of Sage are not supported.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.  

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Update Ledger XML](sage-50-uk-update-ledger-xml):  

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoices>
    <Invoice>
      <Id>123</Id>
      <InvoiceNumber>2352</InvoiceNumber>
    </Invoice>
  </Invoices>
</Company>
```