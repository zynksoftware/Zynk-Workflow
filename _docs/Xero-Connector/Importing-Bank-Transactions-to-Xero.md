---
slug: importing-bank-transactions-to-xero
redirect_from: "/article/906-uploading-bank-transactions-to-xero"
title: Importing Bank Transactions to Xero
---

This task will create new bank transactions in Xero using an XML file.

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

Sample input file containing a bank transaction. It shows the minimum amount of information required to create a bank transaction in Xero:

```xml
<?xml version="1.0"?>
<ArrayOfXeroBankTransaction xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <XeroBankTransaction>
    <ExternalId>5203</ExternalId>
    <Type>SpendOverpayment</Type>
    <LineAmountTypes>NoTax</LineAmountTypes>
    <Contact>
      <Name>ABS Garages Ltd</Name>
    </Contact>
    <LineItems>
      <LineItem>
        <Description>Product</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>10.0000</UnitAmount>
        <AccountCode>2100C</AccountCode>
      </LineItem>
    </LineItems>
    <BankAccount>
      <Code>1200</Code>
    </BankAccount>
  </XeroBankTransaction>
</ArrayOfXeroBankTransaction>
```