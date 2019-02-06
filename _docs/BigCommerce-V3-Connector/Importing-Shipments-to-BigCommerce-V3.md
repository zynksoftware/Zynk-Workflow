---
slug: import-shipments-to-bigcommerce-v3
title: Importing Shipments to BigCommerce V3
---
This task will create new and update existing shipments in your Big Commerce platform.

## Settings
### Connection
_Required_  
The BigCommerce connection to use.See the [Connecting to BigCommerce V3](connecting-to-bigcommerce-v3) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed uploads to.

### Input File
_Required_  
The XML file containing the product updates. These should be stored in the same format as products downloaded using the 'Download Products' task.

### Success File
_Required_  
The XML file to output successful updates to.

### Prevent Reprocessing
_Required_  
Set to true to only process a record once, or set to false to always update records.  Defaults to False.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.  For detailed documentation on the fields please see the [BigCommerce Dev Center](https://developer.bigcommerce.com/api-reference/orders/orders-api/models/ordershipment).

If a `<shipment>` node contains an `<id>` node, it will be treated as an existing shipment and the task will attempt to update it in BigCommerce.

If no `<id>` node is provided for the shipment, it will be treat as a new shipment.

```xml
<?xml version="1.0" encoding="utf-8"?>
<shipments>
  <shipment>
	<order_id>100</order_id>
	<tracking_number>1234</tracking_number>
	<order_address_id>1</order_address_id>
	<items>
	  <item>
	    <order_product_id>1</order_product_id>
	    <quantity>1</quantity>
	  </item>
	</items>
  </shipment>
</shipments>
```