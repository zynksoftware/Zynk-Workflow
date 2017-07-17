---
slug: exporting-payments-from-quickbooks-online
redirect_from: "/article/872-downloading-payments-from-quickbooks-online"
title: Exporting Payments From QuickBooks Online
---


This task will download payments from Quickbooks Online to an XML file.


## Download Payments

### Connection
_Required_  
Select a connection to the Quickbooks Online company you want to use. See [Connecting to QuickBooks Online](connecting-to-quickbooks-online)

### Output File
_Required_  
The file save exported records to.

### Quickbooks Online Settings
See [Common Quickbooks Online Settings](common-quickbooks-online-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Available Filters
- Id
- TxnDate
- CustomerRef
- PaymentRefNum


## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfPayment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfPayment>
        <ExternalId>5230</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>179</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-07-07T15:39:00+01:00</CreateTime>
            <LastUpdatedTime>2016-07-07T15:39:00+01:00</LastUpdatedTime>
          </MetaData>
          <TxnDate>2016-07-07T00:00:00</TxnDate>
          <CurrencyRef name="British Pound Sterling">GBP</CurrencyRef>
          <ExchangeRate>1</ExchangeRate>
          <CustomerRef name="Zynk Software">2068</CustomerRef>
          <DepositToAccountRef>81</DepositToAccountRef>
          <TotalAmt>50</TotalAmt>
          <UnappliedAmt>50</UnappliedAmt>
          <ProcessPayment>false</ProcessPayment>
        </Data>
      </RecordOfPayment>
    </ArrayOfPayment>

```