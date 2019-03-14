---
slug: export-sales-orders-from-peoplevox
title: Export Sales Orders from Peoplevox
---

This task will export sales order information from Peoplevox in XML format, for detailed information see [Peoplevox Sales Order XML](peoplevox-sales-order-xml).  The information is exported using the "Sales orders" integration template as setup through your Peoplevox web application.  You can add search clauses to limit the data that is returned.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### API Call Delay
_Required_  
The number of seconds to wait between sending requests to the Peoplevox API, used when making multiple paged requests to export data.  Defaults to 1.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_item_types.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Zynk Settings
See [Common Task Settings](common-task-settings)

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
		<Site />
		<SalesOrderItems>
			<SalesOrderItem>
				<ItemCode>PROD001</ItemCode>
				<QuantityOrdered>1</QuantityOrdered>
				<RequestedDeliveryDate>2017-07-19 00:00:00</RequestedDeliveryDate>
				<Line></Line>
				<Sequence>1</Sequence>
				<SalePrice>10</SalePrice>
				<Attribute1 />
				<Attribute2 />
				<Attribute3 />
			</SalesOrderItem>
		</SalesOrderItems>
		<OnHold>false</OnHold>
		<Attribute1>01913037279</Attribute1>
		<Attribute2 />
		<Attribute3 />
		<Attribute4 />
		<Attribute5 />
	</SalesOrder>
</SalesOrders>
```
