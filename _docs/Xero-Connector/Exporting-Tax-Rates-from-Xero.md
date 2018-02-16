---
slug: exporting-tax-rates-from-xero
redirect_from: "/article/349-downloading-tax-rates-from-xero"
title: Exporting Tax Rates from Xero
---


This task will download tax rates from Xero in XML format.


### Connection 
_Required_  
The Xero connection use when running this task.

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Filter
_Optional_  
Specify criteria to filter the accounts on e.g. 	`Type == "BANK" AND Name.Contains("Business")`

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample output file showing tax rates:


```xml
    <?xml version="1.0"?>
    <ArrayOfXeroTaxRate>
      <XeroTaxRate>
        <Name>20% (VAT on Expenses)</Name>
        <TaxType>INPUT2</TaxType>
        <TaxComponents>
          <TaxComponent>
            <Name>VAT</Name>
            <Rate>20.0000</Rate>
            <IsCompound>false</IsCompound>
          </TaxComponent>
        </TaxComponents>
        <ReportTaxType>Input</ReportTaxType>
        <Status>Active</Status>
        <CanApplyToAssets>true</CanApplyToAssets>
        <CanApplyToEquity>true</CanApplyToEquity>
        <CanApplyToExpenses>true</CanApplyToExpenses>
        <CanApplyToLiabilities>true</CanApplyToLiabilities>
        <CanApplyToRevenue>false</CanApplyToRevenue>
        <DisplayTaxRate>20.0000</DisplayTaxRate>
        <EffectiveRate>20.0000</EffectiveRate>
      </XeroTaxRate>
      <XeroTaxRate>
        <Name>20% (VAT on Income)</Name>
        <TaxType>OUTPUT2</TaxType>
        <TaxComponents>
          <TaxComponent>
            <Name>VAT</Name>
            <Rate>20.0000</Rate>
            <IsCompound>false</IsCompound>
          </TaxComponent>
        </TaxComponents>
        <ReportTaxType>Output</ReportTaxType>
        <Status>Active</Status>
        <CanApplyToAssets>true</CanApplyToAssets>
        <CanApplyToEquity>true</CanApplyToEquity>
        <CanApplyToExpenses>false</CanApplyToExpenses>
        <CanApplyToLiabilities>true</CanApplyToLiabilities>
        <CanApplyToRevenue>true</CanApplyToRevenue>
        <DisplayTaxRate>20.0000</DisplayTaxRate>
        <EffectiveRate>20.0000</EffectiveRate>
      </XeroTaxRate>
      <XeroTaxRate>
        <Name>No VAT</Name>
        <TaxType>NONE</TaxType>
        <TaxComponents>
          <TaxComponent>
            <Name>VAT</Name>
            <Rate>0.0000</Rate>
            <IsCompound>false</IsCompound>
          </TaxComponent>
        </TaxComponents>
        <ReportTaxType>Output</ReportTaxType>
        <Status>Active</Status>
        <CanApplyToAssets>true</CanApplyToAssets>
        <CanApplyToEquity>true</CanApplyToEquity>
        <CanApplyToExpenses>true</CanApplyToExpenses>
        <CanApplyToLiabilities>true</CanApplyToLiabilities>
        <CanApplyToRevenue>true</CanApplyToRevenue>
        <DisplayTaxRate>0.0000</DisplayTaxRate>
        <EffectiveRate>0.0000</EffectiveRate>
      </XeroTaxRate>
    </ArrayOfXeroTaxRate>

```