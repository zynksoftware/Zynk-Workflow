---
slug: downloading-products-from-sage-one
redirect_from: "/article/854-download-products"
title: Downloading Products from Sage One
---
This task will download Products from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Download Type
_Required_  
Select All, New or Modified.

### Record Id
_Optional_  
Optionally download a specific record by specifying the Sage One id.

### Output File
_Required_  
The file to save the downloaded records to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage One Product XML](sage-one-product-xml) for full documentaion of the XML format.
```xml
<?xml version="1.0"?>
<ArrayOfProduct xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <SageOneRecordId>1757214</SageOneRecordId>
    <Sku>ASOBD</Sku>
    <Name>Another Side Of Bob Dylan</Name>
    <ProductLedgerAccount>
      <SageOneRecordId>2654285</SageOneRecordId>
      <Errors />
      <Name>Sales Type A</Name>
      <NominalCode>4000</NominalCode>
    </ProductLedgerAccount>
    <ProductTaxRate>
      <SageOneRecordId>1</SageOneRecordId>
      <Errors />
      <Name>Standard 20.00%</Name>
      <Rate>20</Rate>
      <SubTaxRates />
    </ProductTaxRate>
    <LastCostPrice>0</LastCostPrice>
    <SalePrice>7.99</SalePrice>
    <SalePriceIncludesTax>true</SalePriceIncludesTax>
  </Product>
</ArrayOfProduct>
```