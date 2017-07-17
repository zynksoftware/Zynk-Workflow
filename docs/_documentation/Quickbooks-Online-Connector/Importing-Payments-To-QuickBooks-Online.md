---
slug: importing-payments-to-quickbooks-online
redirect_from: "/article/881-uploading-payments-to-quickbooks-online"
title: Importing Payments To QuickBooks Online
---


This task will insert new and update existing payments in Quickbooks Online, from an XML file. The logic surrounding inserting/updating payments works as follows:


1. If an Id is provided for the payment, and a payment already exists in Quickbooks with this Id, the existing payment will be updated.
2. If an ExternalId is provided for the payment, and a match is found in Zynk's truth table, the existing payment will be updated.
3. If none of the above conditions are fulfilled, a new payment will be created.


## Upload Payments


### Connection
_Required_  
Select a connection to the Quickbooks Online company you want to use. See [Connecting to QuickBooks Online](connecting-to-quickbooks-online)

### Fail File 
_Required_  
The XML file to output any records to which fail to import to Quickbooks.

### Input File 
_Required_  
The XML file containing the records to import to Quickbooks. See below for a sample input file.

### Success File 
_Required_  
The XML file to output any records to which are successfully imported to Quickbooks.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same records being imported to Quickbooks more than once. Only works on records where an ExternalId is provided in the input file.


## Examples


Sample input file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfPayment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfPayment>
        <ExternalId>123</ExternalId>
        <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
          <TxnDate>2016-07-07T00:00:00</TxnDate>
          <CurrencyRef>GBP</CurrencyRef>
          <ExchangeRate>1</ExchangeRate>
          <CustomerRef name="Zynk Software"></CustomerRef>
          <DepositToAccountRef name="Current"></DepositToAccountRef>
          <TotalAmt>50</TotalAmt>
          <UnappliedAmt>0</UnappliedAmt>
          <ProcessPayment>false</ProcessPayment>
        </Data>
      </RecordOfPayment>
    </ArrayOfPayment>

```