---
slug: updating-order-statuses-in-brightpearl
redirect_from: "/article/updating-order-statuses-in-brightpearl"
title: Updating Order Statuses in Brightpearl
---


This task will update the status of orders in Brightpearl from an XML file.


## Settings

### Connection 
_Required_
The Brightpearl connection to use. See [Connecting to Brightpearl](connecting-to-brightpearl)

### Fail File
_Required_
The file to save failed records to.

### Input File
_Required_
The file containing records to import.

### Success File
_Required_
The file to save successful records to.

### Prevent Reprocessing
_Required_
Set to true to prevent the same records being processed more than once, based on the value of the `externalId` element in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample input file showing an order status update:


```xml
<?xml version="1.0"?>
<ArrayOfOrderStatusUpdate xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<OrderStatusUpdate>
		<externalId>4302</externalId>
		<order>
			<id>25</id>
			<externalId>5230</externalId>
			<reference>upload1234</reference>
		</order>
		<orderStatus>
			<id>19</id>
			<name>Packed</name>
		</orderStatus>
		<orderNote>
			<text>Status updated by Zynk</text>
		</orderNote>
	</OrderStatusUpdate>
</ArrayOfOrderStatusUpdate>
```
