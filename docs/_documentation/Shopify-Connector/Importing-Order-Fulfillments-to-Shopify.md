---
slug: importing-fulfilments-to-shopify
title: Importing fulfillments to Shopify
---
This task will upsert (insert or update) fulfillments to your Shopify store, using the product data in an XML file. If an ID is provided, the existing shipment will be updated, if not, a new one will be created.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output any failed uploads to.

### Input File
_Required_  
The XML file containing the fulfillments. They should be stored in the same format as shown below.

### Success File
_Required_  
The XML file to output successful uploads to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below, showing an order with a single product.

```xml
<?xml version="1.0" encoding="utf-8"?>
<fulfillments>
  <fulfillment>
    <order-id type="integer">4751371664</order-id>
	<tracking-number type="integer">67890</tracking-number>
	<notify-customer type="boolean">false</notify-customer>
	<line-items type="array">
	  <line-item>
	    <id type="integer">8856304976</id>
		<quantity type="integer">2</quantity>
	  </line-item>
	</line-items>
  </fulfillment>
</fulfillments>
```
