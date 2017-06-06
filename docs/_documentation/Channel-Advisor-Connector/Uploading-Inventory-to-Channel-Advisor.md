---
slug: uploading-inventory-to-channel-advisor
redirect_from: "/article/182-uploading-inventory-to-channel-advisor"
title: Uploading Inventory to Channel Advisor
---
This task will update inventory in Channel Advisor, based on an XML file.

## Settings
### Connection
_Required_  
The Channel Advisor connection to use. See the [Connecting to Channel Advisor](connecting-to-channel-advisor) article if you require more information on how to create/manage connections.

### Input File
_Required_  
The input XML file containing the list of inventory items to update.

### Output File
_Required_  
The file to write the results of the update to.

### Page Size
_Optional_  
The amount of inventory items to upload per update call.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInventoryItemQuantityAndPrice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<InventoryItemQuantityAndPrice>
		<Sku>ABC-123</Sku>
		<DistributionCenterCode>London</DistributionCenterCode>
		<Quantity>25</Quantity>
		<PriceInfo>
			<RetailPrice>169.99</RetailPrice>
		</PriceInfo>
	</InventoryItemQuantityAndPrice>
</ArrayOfInventoryItemQuantityAndPrice>
```