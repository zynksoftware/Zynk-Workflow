---
slug: exporting-vendors-from-quickbooks-online
redirect_from: "/article/876-downloading-vendors-from-quickbooks-online"
title: Exporting Vendors From QuickBooks Online
---


This task will download vendors from Quickbooks Online to an XML file.


## Download Vendors

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
- GivenName
- MiddleName
- FamilyName
- Suffix
- DisplayName
- CompanyName
- PrintOnCheckName
- Active
- Balance


## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfVendor xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfVendor>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>23</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2018-01-17T14:22:30+00:00</CreateTime>
            <LastUpdatedTime>2018-01-17T14:22:30+00:00</LastUpdatedTime>
          </MetaData>
          <GivenName>Andrew</GivenName>
          <FamilyName>Haberbosch</FamilyName>
          <CompanyName>Andrew Haberbosch</CompanyName>
          <DisplayName>Andrew Haberbosch</DisplayName>
          <PrintOnCheckName>Andrew Haberbosch</PrintOnCheckName>
          <Active>true</Active>
          <BillAddr>
            <Id>24</Id>
            <Line1>Bromley House</Line1>
            <Line2>Staines</Line2>
            <City>Middlesex</City>
            <PostalCode>TW18 3JY</PostalCode>
            <Lat>51.4314384</Lat>
            <Long>-0.4989863</Long>
          </BillAddr>
          <Balance>0</Balance>
          <Vendor1099>false</Vendor1099>
          <CurrencyRef name="British Pound Sterling">GBP</CurrencyRef>
        </Data>
      </RecordOfVendor>
    </ArrayOfVendor>
```