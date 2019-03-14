---
slug: importing-invoices-to-xero
redirect_from: "/article/352-uploading-invoices-to-xero"
title: Importing Invoices to Xero
---

This task will insert or update invoices in Xero from an XML file.

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

A sample input file with the minimum amount of information required to create an invoice in Xero is shown below. More detailed information about each field can be found in our [API Documentation](xero-invoice-xml).

```xml
<?xml version="1.0"?>
<ArrayOfXeroInvoice>
  <XeroInvoice>
    <ExternalId>1880</ExternalId>
    <Number>TEST2</Number>
    <Contact>
      <ContactNumber>ZYNK001</ContactNumber>
    </Contact>
    <Type>AccountsReceivable</Type>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <Date>2014-08-22T00:00:00</Date>
    <DueDate>2014-09-01T00:00:00</DueDate>
    <CurrencyCode>GBP</CurrencyCode>
    <LineItems>
      <LineItem>
        <Description>Product</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>25.0000</UnitAmount>
        <AccountCode>200</AccountCode>
      </LineItem>
    </LineItems>
  </XeroInvoice>
</ArrayOfXeroInvoice>
```