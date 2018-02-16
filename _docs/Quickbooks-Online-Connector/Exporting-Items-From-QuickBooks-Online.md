---
slug: exporting-items-from-quickbooks-online
redirect_from: "/article/871-downloading-items-from-quickbooks-online"
title: Exporting Items From QuickBooks Online
---


This task will download items from Quickbooks Online to an XML file.


## Download Items

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
- Sku
- Active
- Type


## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfItem xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfItem>
        <ExternalId>7936</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>3</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-04-19T17:01:02+01:00</CreateTime>
            <LastUpdatedTime>2016-04-19T17:01:02+01:00</LastUpdatedTime>
          </MetaData>
          <Name>Catering</Name>
          <Description>Catering -- food &amp;amp; beverage</Description>
          <Active>true</Active>
          <FullyQualifiedName>Catering</FullyQualifiedName>
          <Taxable>false</Taxable>
          <SalesTaxIncluded>false</SalesTaxIncluded>
          <UnitPrice>0</UnitPrice>
          <Type>Service</Type>
          <IncomeAccountRef name="Billable Expenses Income">68</IncomeAccountRef>
          <PurchaseDesc>Catering -- food &amp;amp; beverage</PurchaseDesc>
          <PurchaseTaxIncluded>false</PurchaseTaxIncluded>
          <PurchaseCost>0</PurchaseCost>
          <ExpenseAccountRef name="Cost of Sales - billable expenses">69</ExpenseAccountRef>
          <TrackQtyOnHand>false</TrackQtyOnHand>
          <SalesTaxCodeRef name="SalesTaxCodeRef">3</SalesTaxCodeRef>
          <PurchaseTaxCodeRef name="PurchaseTaxCodeRef">3</PurchaseTaxCodeRef>
        </Data>
      </RecordOfItem>
    </ArrayOfItem>

```