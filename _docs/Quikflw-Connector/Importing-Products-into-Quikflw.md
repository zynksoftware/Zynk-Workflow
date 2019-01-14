---
slug: importing-products-into-quikflw
title: Importing Products into Quikflw
---

This task will create or update products in Quikflw and output a success and a fail file. See below for a sample input file.

If a product with a matching product code exists within Quikflw, the task will update the product. Otherwise, a new product will be created.

### Settings
## Connection
_Required_  
The connection to Quikflw to use. See the [Connecting to Quikflw](connecting-to-quikflw) article if you require further information on how to create/manage the connection to Quikflw.

## Fail File
_Required_   
_Default Value :_ (quikflw_import_products_fail.xml)   
The name of the XML file where failed product uploads are stored.

## Input File
_Required_   
_Default Value :_ (Output from previous task)   
The name of the file containing the records to import into Quikflw.

## Success File
_Required_   
_Default Value :_ (quikflw_import_products_success.xml)   
The name of the XML file where failed product uploads are stored.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Products xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <ProductCode>TEST</ProductCode>
    <Description>This is a test product.</Description>
    <Prices>
      <Price>
        <PriceList>
          <Value>GBP</Value>
        </PriceList>
        <Price>9.99</Price>
        <BreakPoint>0</BreakPoint>
      </Price>
    </Prices>
  </Product>
</Products>
```
