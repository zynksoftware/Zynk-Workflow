---
slug: sage-one-product-xml
title: Sage One Product XML
---
Upload Products allows you to create new and update existing product records in Sage One. You can either provide a field in the XML and set up the task to match product records based on that field, or alternatively you can provide an Id node in your XML.

Any Sage One fields not documented below are not supported with our uploads. 

Sample upload file for creating a product record in Sage One:

```xml
<?xml version="1.0"?>
<ArrayOfProduct xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <Id>BLONDE</Id>
    <Sku>BLONDE</Sku>
    <Name>Blonde On Blonde</Name>
    <ProductLedgerAccount>
      <Name>Sales Type A</Name>
    </ProductLedgerAccount>
    <ProductTaxRate>
      <Rate>20</Rate>
    </ProductTaxRate>
    <LastCostPrice>4.99</LastCostPrice>
    <SalePrice>12.99</SalePrice>
    <SalePriceIncludesTax>true</SalePriceIncludesTax>
    <Notes>Blonde On Blonde, 1966 masterpiece from Bob Dylan. Featuring Just Like A Woman, Visions Of Johanna and I Want You.</Notes>
  </Product>
</ArrayOfProduct>
```

## Product Details
The below information is in relation to the customer details you are able to set using Zynk.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | SageOneRecordId | 1234567 | string | Optional |
| - | Id | BLONDE | string  | Optional |
| Item Code | Sku | BLONDE | string | Optional |
| Description | Name | Blonde on Blonde | string | Required |
| Ledger Account | ProductLedgerAccount/Name  | Sales Type A | string   | Optional  |
| VAT Rate | ProductTaxRate/Rate  | 20  | double   | Optional  |
| Cost Price | LastCostPrice  | 4.99  | double   | Optional  |
| Sales Price | SalePrice  | 12.99  | double  | Optional |
| Includes VAT? | SalePriceIncludesTax  | true  | boolean   | Optional  |
| Notes | Notes  | Blonde On Blonde, 1966 masterpiece from Bob Dylan. Featuring Just Like A Woman, Visions Of Johanna and I Want You.  | string   | Optional  |