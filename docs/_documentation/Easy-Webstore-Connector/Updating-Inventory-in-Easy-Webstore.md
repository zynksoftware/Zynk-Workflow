---
slug: updating-inventory-in-easy-webstore
redirect_from: "/article/208-updating-inventory-in-easy-webstore"
title: Updating Inventory in Easy Webstore
---
This task will update the stock level of products in your store.

## Settings
### Connection
_Required_  
The Easy Webstore connection to use.  See the [Connecting to Easy Webstore](connecting-to-easy-webstore) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed inventory updates to.

### Input File
_Required_  
The XML file containing the inventory updates. The updates should be stored in the same format as products downloaded using the 'Download Products' task, but only the 	`<ID>` or `<ProductCode>` nodes and the `<StockLevel>`node are required for each product.

### Success File
_Required_  
The XML file to output successful inventory updates to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Easy Webstore to Sage 50 Integration](easy-webstore-to-sage-50-integration) article.

Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfProduct xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <ProductCode>PROD001</ProductCode>
    <StockLevel>19</StockLevel>
  </Product>
  <Product>
    <ID>1962374</ID>
    <StockLevel>888</StockLevel>
  </Product>
</ArrayOfProduct>
```