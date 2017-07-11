---
slug: peoplevox-sales-order-xml
title: Peoplevox Sales Order XML
---

Zynk will import the data using the standard fields under Integration Templates that can be ran configured your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Tasks

 * [Import Sales Orders to Peoplevox](import-sales-orders-to-peoplevox)

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

## Identifiers
For inserting or updating records to Peoplevox Zynk uses the SalesOrderNumber field on a SalesOrder.  It is invalid to insert / update a SalesOrder without providing the SalesOrderNumber.  If updating an existing SalesOrder the items will be added or edited depending on what information is provided, it is not possible to remove lines.

## Fields
### SalesOrderNumber
_Required_  
Sales order number.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | SO-123456 | `<SalesOrderNumber>SO-123456</SalesOrderNumber>` |

### Customer
_Optional_  
Customer name or reference.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Andrew Snape | `<Customer>Andrew Snape</Customer>` |

### CustomerPurchaseOrderReferenceNumber
_Optional_  
Customer purchase order reference number.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | SO-ABCDEF | `<CustomerPurchaseOrderReferenceNumber>SO-ABCDEF</CustomerPurchaseOrderReferenceNumber>` |

### ShippingAddressLine1
_Optional_  
Line 1.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | i6 | `<ShippingAddressLine1>i6</ShippingAddressLine1>` |

### ShippingAddressLine2
_Optional_  
Line 2.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | 6 - 8 Charlotte Square | `<ShippingAddressLine2>6 - 8 Charlotte Square</ShippingAddressLine2>` |

### ShippingAddressCity
_Optional_  
City.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Newcastle | `<ShippingAddressCity>Newcastle</ShippingAddressCity>` |

### ShippingAddressRegion
_Optional_  
Region.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Tyne and Wear | `<ShippingAddressRegion>Tyne and Wear</ShippingAddressRegion>` |

### ShippingAddressPostcode
_Optional_  
Post code.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | NE1 4XF | `<ShippingAddressPostcode>NE1 4XF</ShippingAddressPostcode>` |

### ShippingAddressCountry
_Optional_  
Country.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | United Kingdom | `<ShippingAddressCountry>United Kingdom</ShippingAddressCountry>` |

### ShippingAddressReference
_Optional_  
Reference.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | WORK | `<ShippingAddressReference>WORK</ShippingAddressReference>` |

### InvoiceAddressLine1
_Optional_  
Line 1.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | i6 | `<InvoiceAddressLine1>i6</InvoiceAddressLine1` |

### InvoiceAddressLine2
_Optional_  
Line 2.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | 6 - 8 Charlotte Square | `<InvoiceAddressLine2>6 - 8 Charlotte Square</InvoiceAddressLine2>` |

### InvoiceAddressCity
_Optional_  
City.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Newcastle | `<InvoiceAddressCity>Newcastle</InvoiceAddressCity>` |

### InvoiceAddressRegion
_Optional_  
Region.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Tyne and Wear | `<InvoiceAddressRegion>Tyne and Wear</InvoiceAddressRegion>` |

### InvoiceAddressPostcode
_Optional_  
Post code.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | NE1 4XF | `<InvoiceAddressPostcode>NE1 4XF</InvoiceAddressPostcode>` |

### InvoiceAddressCountry
_Optional_  
Country.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | United Kingdom | `<InvoiceAddressCountry>United Kingdom</InvoiceAddressCountry>` |

### InvoiceAddressReference
_Optional_  
Reference.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | WORK | `<InvoiceAddressReference>WORK</InvoiceAddressReference>` |

### IsPartialShipment
_Optional_  
Is partial shipment, defaults to false.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<IsPartialShipment>true</IsPartialShipment>` |

#### Available Values
 * true
 * false

### Status
_Optional_  
Sales order status name, defaults to New.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | New | `<Status>New</Status>` |

#### Available Values
 * New
 * Despatched
 * Closed

### RequestedDeliveryDate
_Optional_  
Requested date in "yyyy-MM-dd HH:mm:ss" format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-20 00:00:00 | `<RequestedDeliveryDate>2017-07-20 00:00:00</RequestedDeliveryDate>` |

### ShippingCost
_Optional_  
Shipping cost.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 5 | `<ShippingCost>5</ShippingCost>` |

### Email
_Required_  
Email.

| Type | Example | XML |
| --- | --- | --- |
| string(500) | support@zynk.com | `<Email>support@zynk.com</Email>` |

### ContactName
_Required_  
Contact name.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Andrew Snape | `<ContactName>Andrew Snape</ContactName>` |

### TotalSale
_Required_  
Total sale.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 18 | `<TotalSale>18</TotalSale>` |

### Discount
_Required_  
Discount.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 0 | `<Discount>0</Discount>` |

### TaxPaid
_Required_  
Tax paid.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 3 | `<TaxPaid>3</TaxPaid>` |

### CreatedDate
_Required_  
Created date in "yyyy-MM-dd HH:mm:ss" format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-11 00:00:00 | `<CreatedDate>2017-07-11 00:00:00</CreatedDate>` |

### PaymentMethod
_Required_  
Payment method.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<PaymentMethod>1</PaymentMethod>` |

### ServiceType
_Required_  
Service type.

| Type | Example | XML |
| --- | --- | --- |
| string(100) |  | `<ServiceType></ServiceType>` |

### ChannelName
_Required_  
Channel name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Website | `<ChannelName>Website</ChannelName>` |

### SalesOrderItems
_Required_  
You need to provide a collection of items as part of the import.

#### ItemCode
_Required_  
Item code.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | PROD001 | `<ItemCode>PROD001</ItemCode>` |

### QuantityOrdered
_Required_  
Quantity ordered.

| Type | Example | XML |
| --- | --- | --- |
| 1 | 1 | `<QuantityOrdered>1</QuantityOrdered>` |

### RequestedDeliveryDate
_Required_  
Requested date in "yyyy-MM-dd HH:mm:ss" format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-19 00:00:00 | `<RequestedDeliveryDate>2017-07-19 00:00:00</RequestedDeliveryDate>` |

### Line
_Required_  
Line.

| Type | Example | XML |
| --- | --- | --- |
| string(16) |  | `<Line></Line>` |

### Sequence
_Required_  
Sequence.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<Sequence>1</Sequence>` |

### SalePrice
_Required_  
Sale price.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 10 | `<SalePrice>10</SalePrice>` |

## Example XML

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