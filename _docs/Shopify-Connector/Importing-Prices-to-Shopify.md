---
slug: importing-prices-to-shopify
title: Importing Prices to Shopify
---
This task will update the product prices on your Shopify store using the product data in an XML file. All variants with a matching SKU will have their price updated.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Prevent Reprocessing
_Required_
Optionally prevent reprocessing the same records by providing an <external_id> in the XML you provide.

### Fail File
_Required_  
The XML file to output any failed imports to.

### Input File
_Required_  
The XML file containing the products. 

### Success File
_Required_  
The XML file to output successful imports to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
```xml
<?xml version="1.0" encoding="utf-8"?>
<products>
  <product>
    <sku>MER99AMP2</sku>
    <price>200</price>
  </product>
</products>
```
