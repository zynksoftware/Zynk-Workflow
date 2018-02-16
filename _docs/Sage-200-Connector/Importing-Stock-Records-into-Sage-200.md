---
slug: importing-stock-records-into-sage-200
redirect_from: "/article/441-import-stock-records"
title: Importing Stock Records into Sage 200
---
This task will import stock records in Zynk XML format to Sage 200 products. If a product already exists (based on finding a matching SKU code), it will be updated, otherwise a new product will be created.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed stock records in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported stock records in Zynk XML format.

### Auto Create Products
_Required_  
Set to 'True' to create products that don't already exist in Sage, or false to only update existing products.

### Default Category
_Required_  
Allows you to specify the default category to use if one is not specified in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a stock record is shown below. See our [Sage 200 Stock Record XML](sage-200-stock-record-xml) for more details on the Zynk XML Product format for Sage 200.

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <Sku>PROD001</Sku>
      <Name>Test Product</Name>
      <GroupCode>1</GroupCode>
      <Status>1</Status>
      <SalePrice>100</SalePrice>
      <UnitOfSale>Each</UnitOfSale>
      <TaxCode>1</TaxCode>
      <Manufacturer>Test Company</Manufacturer>
      <ManufacturerPartNo>1234</ManufacturerPartNo>
      <StandardCostPrice>60</StandardCostPrice>
      <Description>This is a test product</Description>
      <UseDescriptionOnDocs>false</UseDescriptionOnDocs>
      <SearchCategories>
        <SearchCategory>
          <Name>Sync with Website</Name>
          <Value>true</Value>
        </SearchCategory>
      </SearchCategories>
      <UnitWeight>12</UnitWeight>
    </Product>
  </Products>
</Company>
```
