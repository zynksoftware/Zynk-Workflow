---
slug: exporting-accounts-from-quickbooks-online
redirect_from: "/article/866-downloading-accounts-from-quickbooks-online"
title: Exporting Accounts From QuickBooks Online
---


This task will download accounts from Quickbooks Online to an XML file.


## Download Accounts

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
- Name
- SubAccount
- ParentRef
- Description
- FullyQualifiedName
- Active
- Classification
- AccountType
- AccountSubType
- CurrentBalance
- CurrentBalanceWithSubAccounts

## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfAccount xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfAccount>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>3</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-04-06T10:26:44+01:00</CreateTime>
            <LastUpdatedTime>2016-04-20T20:55:58+01:00</LastUpdatedTime>
          </MetaData>
          <Name>Accumulated Depreciation</Name>
          <SubAccount>false</SubAccount>
          <FullyQualifiedName>Accumulated Depreciation</FullyQualifiedName>
          <Active>true</Active>
          <Classification>Asset</Classification>
          <AccountType>Fixed Asset</AccountType>
          <AccountSubType>AccumulatedDepreciation</AccountSubType>
          <CurrentBalance>-299.97</CurrentBalance>
          <CurrentBalanceWithSubAccounts>-299.97</CurrentBalanceWithSubAccounts>
          <CurrencyRef name="British Pound Sterling">GBP</CurrencyRef>
        </Data>
      </RecordOfAccount>
    </ArrayOfAccount>

```