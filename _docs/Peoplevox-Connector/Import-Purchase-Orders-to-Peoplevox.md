---
slug: import-purchase-orders-to-peoplevox
title: Import Purchase Orders to Peoplevox
---

This task will import purchase order information to Peoplevox in XML format, for detailed information see [Peoplevox Purchase Order XML](peoplevox-purchase-order-xml).  The information is imported using the standard fields under Integration Templates that can be configured through your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Integration Templates
### Purchase Order
[Download Template](/assets/resources/peoplevox/purchase_order.csv)

```csv
PurchaseOrderNumber,Status,Reference,Supplier,AddressLine1,AddressLine2,AddressCity,AddressRegion,AddressPostcode,AddressCountry,AddressReference,RequestedDeliveryDate,SubmittedDate,User,EndDate,ExpectedDeliveryDate
```

### Purchase Order Item
[Download Template](/assets/resources/peoplevox/purchase_order_item.csv)

```csv
PurchaseOrderNumber,ItemCode,Status,Quantity,RequestedDeliveryDate,Line,Sequence,CostPrice,ExpectededDeliveryDate
```

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### Input File
_Required_  
The name or full path to the file the data to be imported will be read from.  Defaults to `peoplevox_import_purchase_orders.xml`, which should exist in the working directory of the Workflow.

### Success File
_Required_  
The name or full path to the file successfully imported records will be saved to.  Defaults to `peoplevox_import_purchase_orders_success.xml`, which will be created in the working directory of the Workflow.

### Fail File
_Required_  
The name or full path to the file falied records will be saved to.  Defaults to `peoplevox_import_purchase_orders_fail.xml`, which will be created in the working directory of the Workflow.

### Prevent Reprocessing
_Required_  
Set to true if you only want to process a record once, or false to update every time.  Defaults to False.

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

## Example XML
Example input file, for detailed information see [Peoplevox Purchase Order XML](peoplevox-purchase-order-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<PurchaseOrders>
	<PurchaseOrder>
		<PurchaseOrderNumber>PO-123456</PurchaseOrderNumber>
		<Status>Pending</Status>
		<Reference>PO-ABCDEF</Reference>
		<Supplier>Andrew Snape</Supplier>
		<AddressLine1>i6</AddressLine1>
		<AddressLine2>6 - 8 Charlotte Square</AddressLine2>
		<AddressCity>Newcastle</AddressCity>
		<AddressRegion>Tyne and Wear</AddressRegion>
		<AddressPostcode>NE1 4XF</AddressPostcode>
		<AddressCountry>United Kingdom</AddressCountry>
		<AddressReference>WORK</AddressReference>
		<RequestedDeliveryDate>2017-07-20 00:00:00</RequestedDeliveryDate>
		<SubmittedDate>2017-07-10 00:00:00</SubmittedDate>
		<EndDate>2017-08-20 00:00:00</EndDate>
		<ExpectedDeliveryDate>2017-07-18 00:00:00</ExpectedDeliveryDate>
		<PurchaseOrderItems>
			<PurchaseOrderItem>
				<ItemCode>PROD001</ItemCode>
				<Status>Pending</Status>
				<Quantity>2</Quantity>
				<RequestedDeliveryDate>2017-07-19 00:00:00</RequestedDeliveryDate>
				<Line>PROD001</Line>
				<Sequence>1</Sequence>
				<CostPrice>10</CostPrice>
				<ExpectededDeliveryDate>2017-07-21 00:00:00</ExpectededDeliveryDate>
			</PurchaseOrderItem>
		</PurchaseOrderItems>
	</PurchaseOrder>
</PurchaseOrders>
```