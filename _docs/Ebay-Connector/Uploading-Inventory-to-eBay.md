---
slug: uploading-inventory-to-ebay
redirect_from: "/article/777-uploading-inventory-to-ebay"
title: Uploading Inventory to eBay
---
This task will upload inventory status information to eBay in XML format. Both single and multi-variation listings are supported.

Depending upon the inventory tracking method on each listing, you must provide either the ItemID or the SKU of the listing to update. When dealing with a multi-variation listing using the ItemID tracking method, both the SKU and ItemID must be provided. The task includes an option to automatically look up the ItemID if this cannot be provided, see below for more details.

## Settings
### Connection
_Required_  
The eBay connection to use. bSee the [Connecting to eBay](connecting-to-ebay) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed inventory updates to.

### Input File
_Required_  
The XML file containing the inventory to update.

### Success File
_Required_  
The XML to output successful inventory updates to.

### Lookup Item IDs
_Required_  
Enable this option when dealing with listings where the inventory tracking method is ItemID, but you are unable to provide the ItemID in the input file. This will instruct the task to search for an active listing based on SKU code, and retrieve the ItemID.

When using this option and dealing with multi-variation listings, you must provide both the SKU of the main listing and variation. The variation SKU must be specified in the SKU element, and the main listing SKU in the ParentSKU element in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [eBay to Sage 50 Integration](ebay-to-sage-to-uk-integration) article.

Sample input file:
```xml
<?xml version="1.0"?>
<ArrayOfInventoryStatusType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <InventoryStatusType>
        <ItemID xmlns="urn:ebay:apis:eBLBaseComponents">110176306105</ItemID>
        <SKU xmlns="urn:ebay:apis:eBLBaseComponents">SKU123-RED</SKU>
        <ParentSKU xmlns="urn:ebay:apis:eBLBaseComponents">SKU123</ParentSKU><!-- Used in conjunction with the Lookup Item IDs setting. Must be provided when dealing with a multi-variation listing and ItemID is not provided -->
        <Quantity xmlns="urn:ebay:apis:eBLBaseComponents">2</Quantity>
    </InventoryStatusType><br>
</ArrayOfInventoryStatusType>
```

Sample output file:

```xml
<?xml version="1.0"?>
<ArrayOfInventoryStatusType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <InventoryStatusType>
    <SKU xmlns="urn:ebay:apis:eBLBaseComponents">SKU123-RED</SKU>
    <ItemID xmlns="urn:ebay:apis:eBLBaseComponents">110176306105</ItemID>
    <StartPrice currencyID="AFA" xmlns="urn:ebay:apis:eBLBaseComponents">25</StartPrice>
    <Quantity xmlns="urn:ebay:apis:eBLBaseComponents">4</Quantity>
  </InventoryStatusType>
</ArrayOfInventoryStatusType>
```
