---
slug: importing-credit-notes-to-xero
redirect_from: "/article/351-uploading-credit-notes-to-xero"
title: Importing Credit Notes to Xero
---

This task will insert or update credit notes in Xero from an XML file.

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

A sample input file containing is shown below. It shows the minimum amount of information required to create a credit note in Xero. More detailed information about each field can be found in our [API Documentation](xero-credit-note-xml).

```xml
<?xml version="1.0"?>
<ArrayOfXeroCreditNote>
  <XeroCreditNote>
    <ExternalId>5230</ExternalId>
    <Number>ABC-123</Number>
    <Type>AccountsPayable</Type>
    <Contact>
      <Name>Zynk Software</Name>
    </Contact>
    <Date>2014-07-07T00:00:00</Date>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <CurrencyCode>GBP</CurrencyCode>
    <LineItems>
      <LineItem>
        <Description>MacBook - White</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>25.00</UnitAmount>
        <AccountCode>720</AccountCode>
        <Tracking />
      </LineItem>
    </LineItems>
  </XeroCreditNote>
</ArrayOfXeroCreditNote>
```