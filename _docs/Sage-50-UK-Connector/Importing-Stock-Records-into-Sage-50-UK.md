---
slug: importing-stock-records-into-sage-50-uk
redirect_from: "/article/417-importing-stock-records-into-sage-50-uk"
title: Importing Stock Records into Sage 50 UK
---
This task will import stock records to Sage 50 that is supplied in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Stock Record XML](sage-50-uk-stock-record-xml):  

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <Sku>PROD001</Sku>
      <Name>Test Product</Name>
      <SalePrice>100</SalePrice>
      <Publish>true</Publish>
      <TaxCode>1</TaxCode>
      <UnitOfSale>Each</UnitOfSale>
    </Product>
  </Products>
</Company>
```