---
slug: exporting-tax-codes-from-quickbooks-online
redirect_from: "/article/875-downloading-tax-codes-from-quickbooks-online"
title: Exporting Tax Codes From QuickBooks Online
---


This task will download tax codes from Quickbooks Online to an XML file.


## Download Tax Codes

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
- Description
- Active

## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfTaxCode xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfTaxCode>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>3</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-04-15T22:12:44+01:00</CreateTime>
            <LastUpdatedTime>2016-04-15T22:12:44+01:00</LastUpdatedTime>
          </MetaData>
          <Name>20.0% S</Name>
          <Description>Standard</Description>
          <Active>true</Active>
          <Taxable>true</Taxable>
          <TaxGroup>true</TaxGroup>
          <SalesTaxRateList>
            <TaxRateDetail>
              <TaxRateRef name="SS-20.0">4</TaxRateRef>
              <TaxTypeApplicable>TaxOnAmount</TaxTypeApplicable>
              <TaxOrder>0</TaxOrder>
            </TaxRateDetail>
          </SalesTaxRateList>
          <PurchaseTaxRateList>
            <TaxRateDetail>
              <TaxRateRef name="SP-20.0">3</TaxRateRef>
              <TaxTypeApplicable>TaxOnAmount</TaxTypeApplicable>
              <TaxOrder>0</TaxOrder>
            </TaxRateDetail>
          </PurchaseTaxRateList>
        </Data>
      </RecordOfTaxCode>
    </ArrayOfTaxCode>

```