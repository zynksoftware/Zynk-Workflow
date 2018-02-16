---
slug: uploading-products-to-shopify
redirect_from: "/article/312-uploading-products-to-shopify"
title: Uploading Products to Shopify
---
This task will upsert (insert or update) products to your Shopify store, using the product data in an XML file. If no product ID is provided for a product in the input file, that task will insert a new product into Shopify. If an ID is provided, the existing product will be updated.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output any failed uploads to.

### Input File
_Required_  
The XML file containing the products. They should be stored in the same format as the results returned by the Download Products task.

### Success File
_Required_  
The XML file to output successful uploads to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below, showing two products. The first is an example of updating an existing product, and the second is an example of creating a new product.
```xml
<?xml version="1.0" encoding="utf-8"?>
<products type="array">
  <product>
    <!--update -->
    <id type="integer">100040852</id> 
    <published type="boolean">false</published>
  </product>
  <product>
    <!-- insert -->
    <title>My New Product</title>
    <body-html><strong>Good snowboard!</strong></body-html>
    <vendor>Burton</vendor>
    <product-type>Snowboard</product-type>
    <variants type="array">
      <variant>
        <option1>First</option1>
        <price>10.00</price>
      </variant>
      <variant>
        <option1>Second</option1>
        <price>20.00</price>
      </variant>
    </variants>
  </product>
</products>
```