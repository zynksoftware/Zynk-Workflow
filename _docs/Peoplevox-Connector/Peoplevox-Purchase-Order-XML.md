---
slug: peoplevox-purchase-order-xml
title: Peoplevox Purchase Order XML
---

Zynk will import the data using the standard fields under Integration Templates that can be ran configured your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Tasks

 * [Import Purchase Orders to Peoplevox](import-purchase-orders-to-peoplevox)

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

## Identifiers
For inserting or updating records to Peoplevox Zynk uses the PurchaseOrderNumber field on a PurchaseOrder.  It is invalid to insert / update a PurchaseOrder without providing the PurchaseOrderNumber.  If updating an existing PurchaseOrder the items will be added or edited depending on what information is provided, it is not possible to remove lines.

## Fields
### PurchaseOrderNumber
_Required_  
Purchase order number.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | PO-123456 | `<PurchaseOrderNumber>PO-123456</PurchaseOrderNumber>` |

### Status
_Optional_  
Status.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Pending | `<Status>Pending</Status>` |

#### Available Values
 * Pending
 * Cancelled
 * Deleted

### Reference
_Optional_  
Reference.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | PO-ABCDEF | `<Reference>PO-ABCDEF</Reference>` |

### Supplier
_Optional_  
Supplier name or external reference.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Andrew Snape | `<Supplier>Andrew Snape</Supplier>` |

### AddressLine1
_Optional_  
Line 1.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | i6 | `<AddressLine1>i6</AddressLine1>` |

### AddressLine2
_Optional_  
Line 2.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | 6 - 8 Charlotte Square | `<AddressLine2>6 - 8 Charlotte Square</AddressLine2>` |

### AddressCity
_Optional_  
City.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Newcastle | `<AddressCity>Newcastle</AddressCity>` |

### AddressRegion
_Optional_  
Region.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Tyne and Wear | `<AddressRegion>Tyne and Wear</AddressRegion>` |

### AddressPostcode
_Optional_  
Post code.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | NE1 4XF | `<AddressPostcode>NE1 4XF</AddressPostcode>` |

### AddressCountry
_Optional_  
Country.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | United Kingdom | `<AddressCountry>United Kingdom</AddressCountry>` |

### AddressReference
_Optional_  
Reference.

| Type | Example | XML |
| --- | --- | --- |
| string(100) | WORK | `<AddressReference>WORK</AddressReference>` |

### RequestedDeliveryDate
_Optional_  
Requested date in "yyyy-MM-dd HH:mm:ss" format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-20 00:00:00 | `<RequestedDeliveryDate>2017-07-20 00:00:00</RequestedDeliveryDate>` |

### SubmittedDate
_Optional_  
Submitted date in "yyyy-MM-dd HH:mm:ss" format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-10 00:00:00 | `<SubmittedDate>2017-07-10 00:00:00</SubmittedDate>` |

### EndDate
_Optional_  
End date in "yyyy-MM-dd HH:mm:ss" format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-08-20 00:00:00 | `<EndDate>2017-08-20 00:00:00</EndDate>` |

### ExpectedDeliveryDate
_Optional_  
Expected delivery date in "yyyy-MM-dd HH:mm:ss" format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-18 00:00:00 | `<ExpectedDeliveryDate>2017-07-18 00:00:00</ExpectedDeliveryDate>` |

### PurchaseOrderItems
_Required_  
You need to provide a collection of items as part of the import.

#### ItemCode
_Required_  
Item code

| Type | Example | XML |
| --- | --- | --- |
| string(50) | PROD001 | `<ItemCode>PROD001</ItemCode>` |

#### Status
_Optional_  
Purchase order item type status name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Pending | `<Status>Pending</Status>` |

#### Available Values
 * Pending
 * Closed

#### Quantity
_Optional_  
Quantity.

| Type | Example | XML |
| --- | --- | --- |
| int | 2 | `<Quantity>2</Quantity>` |

#### RequestedDeliveryDate
_Optional_  
Requested delivery date in yyyy-MM-dd HH:mm:ss format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-19 00:00:00 | `<RequestedDeliveryDate>2017-07-19 00:00:00</RequestedDeliveryDate>` |

#### Line
_Optional_  
Line.

| Type | Example | XML |
| --- | --- | --- |
| string(16) |  | `<Line></Line>` |

#### Sequence
_Optional_  
Sequence.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<Sequence>1</Sequence>` |

#### CostPrice
_Optional_  
Cost price.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 10 | `<CostPrice>10</CostPrice>` |

#### ExpectededDeliveryDate
_Optional_  
Expected delivery date in yyyy-MM-dd HH:mm:ss format.

| Type | Example | XML |
| --- | --- | --- |
| string(19) | 2017-07-21 00:00:00 | `<ExpectededDeliveryDate>2017-07-21 00:00:00</ExpectededDeliveryDate>` |

## Example XML

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
				<Line></Line>
				<Sequence>1</Sequence>
				<CostPrice>10</CostPrice>
				<ExpectededDeliveryDate>2017-07-21 00:00:00</ExpectededDeliveryDate>
			</PurchaseOrderItem>
		</PurchaseOrderItems>
	</PurchaseOrder>
</PurchaseOrders>
```