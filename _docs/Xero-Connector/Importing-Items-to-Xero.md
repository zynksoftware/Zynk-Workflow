---
slug: importing-items-to-xero
redirect_from: "/article/354-uploading-items-to-xero"
title: Importing Items to Xero
---

This task will insert or update items (products) in Xero.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Fail File
_Required_  
The file to save failed record imports to.

### Input File
_Required_  
The file containing the bank transactions to upload to Xero.

### Success File
_Required_  
The file to save successful record imports to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once, based on the ExternalId provided in the input XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples

A sample input file is shown below. More detailed information about each field can be found in our [API Documentation](xero-item-xml).

```xml
<?xml version="1.0"?>
<ArrayOfXeroItem>
  <XeroItem>
    <ExternalId>7814</ExternalId>
    <Code>PROD001</Code>
    <Description>Test Product</Description>
    <SalesDetails>
      <UnitPrice>20.00</UnitPrice>
      <AccountCode>200</AccountCode>
    </SalesDetails>
  </XeroItem>
</ArrayOfXeroItem>
```