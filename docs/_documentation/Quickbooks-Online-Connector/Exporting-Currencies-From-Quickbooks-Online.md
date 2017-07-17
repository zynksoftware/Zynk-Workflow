---
slug: exporting-currencies-from-quickbooks-online
redirect_from: "/article/868-downloading-currencies-from-quickbooks-online"
title: Exporting Currencies From Quickbooks Online
---


This task will download currencies from Quickbooks Online to an XML file.


## Download Currencies

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
- Active

## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfCompanyCurrency xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfCompanyCurrency>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>2</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-04-15T22:12:17+01:00</CreateTime>
            <LastUpdatedTime>2016-04-15T22:12:17+01:00</LastUpdatedTime>
          </MetaData>
          <Code>EUR</Code>
          <Name>Euro</Name>
          <Active>true</Active>
        </Data>
      </RecordOfCompanyCurrency>
      <RecordOfCompanyCurrency>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>1</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-04-15T22:12:17+01:00</CreateTime>
            <LastUpdatedTime>2016-04-15T22:12:17+01:00</LastUpdatedTime>
          </MetaData>
          <Code>USD</Code>
          <Name>United States Dollar</Name>
          <Active>true</Active>
        </Data>
      </RecordOfCompanyCurrency>
    </ArrayOfCompanyCurrency>
```