---
slug: updating-inventory-in-magento-v2
redirect_from: "/article/updating-inventory-in-magento-v2"
title: Updating Inventory in Magento V2
---
This task will update inventory in Magento. See below for a sample input file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

## Fail File
_Required_  
The XML file to save failed inventory updates to. The data will be written in the same format as the input file.

## Input File
_Required_  
The XML file containing the inventory to be updated in Magento.

## Success File
_Required_  
The XML file to save successful inventory updates to. The data will be written in the same format as the input file.

## Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. This will update the stock level of the product with SKU '24-MB01' to 198.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfStockItem>
  <StockItem>
    <sku>24-MB01</sku>
    <qty>198.00000</qty>
  </StockItem>
</ArrayOfStockItem>
```
