---
slug: sage-one-service-xml
title: Sage One Service XML
---
Upload Services allows you to create new and update existing service records in Sage One. You can either provide a field in the XML and set up the task to match service records based on that field, or alternatively you can provide an Id node in your XML.  

Any Sage One fields not documented below are not supported with our uploads. 

Sample upload file for creating a service record in Sage One:

```xml
<?xml version="1.0"?>
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

## Service Details
The below information is in relation to the customer details you are able to set using Zynk.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | SageOneRecordId | 1234567 | string | Optional |
| - | Id | RS01 | string  | Optional |
| Description | Name | The Beatles - Rubber Soul | string | Required |
| Cost Price | LastCostPrice  | 12.99 | double   | Optional  |
| Sales Price | SalePrice  | 19.99  | double  | Optional  |
| Includes VAT? | SalePriceIncludesTax  | true  | boolean   | Optional  |
| Includes VAT? | PeriodRateIncludesTax  | true  | boolean   | Optional  |
| Ledger Account | ServiceLedgerAccount/Name  | Sales Type A | string   | Optional  |
| VAT Rate | ServiceTaxRate/Rate  | 20  | double   | Optional  |
| Rate Frequency | PeriodRate/PeriodRateType  | Annually  | enum   | Optional  |
| Notes | Notes  | Blonde On Blonde, 1966 masterpiece from Bob Dylan. Featuring Just Like A Woman, Visions Of Johanna and I Want You.  | string   | Optional  |