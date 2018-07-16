---
slug: uploading-inventory-to-ebay
redirect_from: "/article/777-uploading-inventory-to-ebay"
title: Uploading Inventory to eBay
---
This task will upload inventory status information to eBay in XML format.  You must provide either the ItemID or the SKU of the product to update, the SKU is provided but does not match only the ItemID will be used.

As mentioned above, it is possible to update your inventory with a SKU. However, when you create the listing in eBay for your product you must set the InventoryTrackingMethod to SKU. This is a limitation of the eBay API.

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
        <!--<SKU xmlns="urn:ebay:apis:eBLBaseComponents>SKU123</SKU>-->
        <Quantity xmlns="urn:ebay:apis:eBLBaseComponents">2</Quantity>
    </InventoryStatusType><br>
</ArrayOfInventoryStatusType>
```

Sample output file:

```xml
<?xml version="1.0"?>
<ArrayOfInventoryStatusType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <InventoryStatusType>
    <SKU xmlns="urn:ebay:apis:eBLBaseComponents" />
    <ItemID xmlns="urn:ebay:apis:eBLBaseComponents">110176306105</ItemID>
    <StartPrice currencyID="AFA" xmlns="urn:ebay:apis:eBLBaseComponents">25</StartPrice>
    <Quantity xmlns="urn:ebay:apis:eBLBaseComponents">4</Quantity>
  </InventoryStatusType>
</ArrayOfInventoryStatusType>
```
