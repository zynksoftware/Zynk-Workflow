---
slug: importing-inventory-to-shopify
redirect_from: "/article/importing-inventory-to-shopify"
title: Importing Inventory to Shopify
---
This task will update the inventory on your Shopify store using the product data in an XML file.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output any failed uploads to.

### Input File
_Required_  
The XML file containing the products. 

### Success File
_Required_  
The XML file to output successful uploads to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below which updates an existing products inventory levels.
```xml
<?xml version="1.0" encoding="utf-8"?>
<variants>
    <variant>
        <sku>MER99AMP2</sku>
        <inventory-management>shopify</inventory-management> <!-- shopify | blank -->
        <inventory-policy>continue</inventory-policy> <!-- deny | continue -->
        <inventory-quantity>15</inventory-quantity>
        <old-inventory-quantity>10</old-inventory-quantity>
    </variant>
</variants>
```
