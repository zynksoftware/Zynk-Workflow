---
slug: importing-payments-to-xero
redirect_from: "/article/350-uploading-payments-to-xero"
title: Importing Payments to Xero
---

This task will create new payments in Xero using an XML file.

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

Sample input file containing a payment for invoice number 'TEST1'. It shows the minimum amount of information required to create a payment in Xero:

```xml
<?xml version="1.0"?>
<ArrayOfXeroPayment>
  <XeroPayment>
    <ExternalId>8928</ExternalId>
    <Date>2013-09-10T00:00:00</Date>
    <Amount>5.00</Amount>
    <Reference>TEST1-PAY1</Reference>
    <Invoice>
      <Number>TEST1</Number>
    </Invoice>
    <Account>
      <Code>090</Code>
    </Account>
  </XeroPayment>
</ArrayOfXeroPayment>
```