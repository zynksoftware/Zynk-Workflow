---
slug: uploading-products-to-sage-one
redirect_from: "/article/817-upload-products"
title: Uploading Products to Sage One
---
This task will upload products that are supplied in the [Sage One Product XML](sage-one-product-xml) format.

## Fields
The below fields in bold are required when creating a product, the other fields are optional when creating and updating. Please note, if you do not provide an Id field when creating a product Zynk will be unable to update that product when it is next uploaded.

* __Name__
* __ProductLedgerAccount/Id__ or __ProductLedgerAccount/Name__ or __Default Ledger Account (Task Setting)__
* __ProductTaxRate/Id__ or __ProductTaxRate/Rate__ or __Default Tax Rate (Task Setting)__
* LastCostPrice
* SalePrice
* SalePriceIncludesTax
* Notes

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Default Ledger Account
_Required_  
The ledger account to use when one is not supplied on the record in your input file.

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
A sample input file is shown below. See [Sage One Product XML](sage-one-product-xml) for full documentation of the XML.
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