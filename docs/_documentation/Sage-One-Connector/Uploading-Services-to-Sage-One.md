---
slug: uploading-services-to-sage-one
redirect_from: "/article/818-upload-services"
title: Uploading Services to Sage One
---
This task will upload services that are supplied in the [Sage One XML](sage-one-xml) format.

## Required Fields

The below fields in bold are required when creating a service, the other fields are optional when creating or updating. Please note, if you do not provide an Id field when creating a service Zynk will be unable to update that service when it is next uploaded.

* __Name__
* __ServiceLedgerAccount/Id__ or __ServiceLedgerAccount/Name__ or __Default Ledger Account__
* __PeriodRate/Id__ or __PeriodRate/PeriodRateType__ or __Default Period Rate__
* __ServiceTaxRate/Id__ or __ServiceTaxRate/Name__ or __Default Tax Rate__
* PeriodRateIncludesTax
* SalePrice
* Notes

*Service code is not supported by the Sage One API, therefore Zynk cannot support this field.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Default Ledger Account
_Required_  
The ledger account to use when one is not supplied on the record in your input file.

### Default Period Rate
_Required_  
The period rate to use when one is not supplied on the record in your input file.

### Default Tax Rate
_Required_  
The tax rate to use when one is not supplied on the record in your input file.

### Fail File
_Required_  
The name of a file for “failed” imports to be sent to.

### Input File
_Required_  
The source file that you want to import in Zynk XML format.

### Success File
_Required_  
The name of a file for “successful” imports to be sent to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage One Service XML](sage-one-service-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfService xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Service>
    <Id>RS01</Id>
    <Name>The Beatles - Rubber Soul</Name>
    <LastCostPrice>12.99</LastCostPrice>
    <SalePrice>19.99</SalePrice>
    <SalePriceIncludesTax>true</SalePriceIncludesTax>
    <PeriodRateIncludesTax>true</PeriodRateIncludesTax>
    <ServiceLedgerAccount>
      <Name>Sales Type A</Name>
    </ServiceLedgerAccount>
    <ServiceTaxRate>
      <Rate>20</Rate>
    </ServiceTaxRate>
    <PeriodRate>
      <PeriodRateType>Annually</PeriodRateType>
    </PeriodRate>
  </Service>
</ArrayOfService>
```