---
slug: import-shipments-to-bigcommerce
title: Importing Shipments to BigCommerce
---
This task will create new and update existing shipments in your Big Commerce platform.

## Settings
### Connection
_Required_  
The BigCommerce connection to use. See the [Connecting to BigCommerce](connecting-to-bigcommerce) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed imports to.

### Input File
_Required_  
The XML file containing the shipments. These should be stored in the same format as detailed below.

If a `<shipment>` node contains an `<id>` node, it will be treated as an existing shipment and the task will attempt to update it in BigCommerce. When updating existing products, please note that the `<rating_total>`, `<rating_count>`, `<number_sold>`, `<date_created>`, `<date_modified>`, `<date_last_imported>` and `<custom_url>` nodes are read-only and will result in an error if you try to update them.

If no `<id>` node is provided for the shipment, it will be treat as a new shipment.

### Success File
_Required_  
The XML file to output successful imports to.

## Examples
Sample input file:

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