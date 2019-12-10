---
slug: import-sales-orders-to-peoplevox
title: Import Sales Orders to Peoplevox
---

This task will import sales order information to Peoplevox in XML format, for detailed information see [Peoplevox Sales Order XML](peoplevox-sales-order-xml).  The information is imported using the standard fields under Integration Templates that can be configured through your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Integration Templates
### Sales Order
[Download Template](/assets/resources/peoplevox/sales_order.csv)

```csv
SalesOrderNumber,Customer,CustomerPurchaseOrderReferenceNumber,ShippingAddressLine1,ShippingAddressLine2,ShippingAddressCity,ShippingAddressRegion,ShippingAddressPostcode,ShippingAddressCountry,ShippingAddressReference,InvoiceAddressLine1,InvoiceAddressLine2,InvoiceAddressCity,InvoiceAddressRegion,InvoiceAddressPostcode,InvoiceAddressCountry,InvoiceAddressReference,IsPartialShipment,Status,RequestedDeliveryDate,ShippingCost,Email,ContactName,TotalSale,Discount,TaxPaid,CreatedDate,PaymentMethod,ServiceType,ChannelName
```

### Sales Order Item
[Download Template](/assets/resources/peoplevox/sales_order_item.csv)

```csv
SalesOrderNumber,ItemCode,QuantityOrdered,RequestedDeliveryDate,Line,Sequence,SalePrice
```

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### Validate Templates
_Required_
Optionally valid the template configured in Peoplevox against the Zynk object. Any fields that are not set up on the template or that do not match the Zynk object will be logged out as a warning.

### Input File
_Required_  
The name or full path to the file the data to be imported will be read from.  Defaults to `peoplevox_import_sales_orders.xml`, which should exist in the working directory of the Workflow.

### Success File
_Required_  
The name or full path to the file successfully imported records will be saved to.  Defaults to `peoplevox_import_sales_orders_success.xml`, which will be created in the working directory of the Workflow.

### Fail File
_Required_  
The name or full path to the file falied records will be saved to.  Defaults to `peoplevox_import_sales_orders_fail.xml`, which will be created in the working directory of the Workflow.

### Prevent Reprocessing
_Required_  
Set to true if you only want to process a record once, or false to update every time.  Defaults to False.

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Retry Settings
_Optional_
See [Retry Settings](retry-settings).

## Example XML
Example input file, for detailed information see [Peoplevox Sales Order XML](peoplevox-sales-order-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesOrders>
	<SalesOrder>
		<SalesOrderNumber>SO-123456</SalesOrderNumber>
		<Customer>Andrew Snape</Customer>
		<CustomerPurchaseOrderReferenceNumber>SO-ABCDEF</CustomerPurchaseOrderReferenceNumber>
		<ShippingAddressLine1>i6</ShippingAddressLine1>
		<ShippingAddressLine2>6 - 8 Charlotte Square</ShippingAddressLine2>
		<ShippingAddressCity>Newcastle</ShippingAddressCity>
		<ShippingAddressRegion>Tyne and Wear</ShippingAddressRegion>
		<ShippingAddressPostcode>NE1 4XF</ShippingAddressPostcode>
		<ShippingAddressCountry>United Kingdom</ShippingAddressCountry>
		<ShippingAddressReference>WORK</ShippingAddressReference>
		<InvoiceAddressLine1>i6</InvoiceAddressLine1>
		<InvoiceAddressLine2>6 - 8 Charlotte Square</InvoiceAddressLine2>
		<InvoiceAddressCity>Newcastle</InvoiceAddressCity>
		<InvoiceAddressRegion>Tyne and Wear</InvoiceAddressRegion>
		<InvoiceAddressPostcode>NE1 4XF</InvoiceAddressPostcode>
		<InvoiceAddressCountry>United Kingdom</InvoiceAddressCountry>
		<InvoiceAddressReference>WORK</InvoiceAddressReference>
		<IsPartialShipment>true</IsPartialShipment>
		<Status>New</Status>
		<RequestedDeliveryDate>2017-07-20 00:00:00</RequestedDeliveryDate>
		<ShippingCost>5</ShippingCost>
		<Email>support@zynk.com</Email>
		<ContactName>Andrew Snape</ContactName>
		<TotalSale>18</TotalSale>
		<Discount>0</Discount>
		<TaxPaid>3</TaxPaid>
		<CreatedDate>2017-07-11 00:00:00</CreatedDate>
		<PaymentMethod>1</PaymentMethod>
		<ServiceType></ServiceType>
		<ChannelName>Website</ChannelName>
		<Site>PrimarySite</Site>
		<SalesOrderItems>
			<SalesOrderItem>
				<ItemCode>PROD001</ItemCode>
				<QuantityOrdered>1</QuantityOrdered>
				<RequestedDeliveryDate>2017-07-19 00:00:00</RequestedDeliveryDate>
				<Line></Line>
				<Sequence>1</Sequence>
				<SalePrice>10</SalePrice>
			</SalesOrderItem>
		</SalesOrderItems>
	</SalesOrder>
</SalesOrders>
```
