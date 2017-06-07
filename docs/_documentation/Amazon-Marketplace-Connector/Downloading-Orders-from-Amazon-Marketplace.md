---
slug: downloading-orders-from-amazon-marketplace
redirect_from: "/article/147-downloading-orders-from-amazon-marketplace"
title: Downloading Orders from Amazon Marketplace
---
This task will provide a list of updated orders in XML format from a specified Amazon MWS account, in an XML format.

## Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

### Download Date
_Required_  
The initial date to download orders from. Any orders placed before this date will not download, even if they are updated. This can be used to prevent orders which have already been handled manually from being downloaded.

### Download From
_Required_  
The rolling date to download updated orders from. This will automatically update each time the task runs. TIP: If you want to re-download old orders, change the Download From property

### Fulfilment Channel
_Required_  
The fulfilment channel of orders to download from Amazon. Choose whether to download orders fulfilled by Amazon (AFN), not fulfilled by Amazon (MFN) or all (All).
Defaults to all fulfilment channels.

### Order Status
_Required_  
The status of when you want to download the order from Amazon. Choose from Pending, Unshipped, PartiallyShipped, Shipped, Cancelled or Unfulfillable.

### Output File
_Required_  
The name of the file to export the downloaded orders to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Amazon to Sage Integration article](amazon-to-sage-integration).

Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders>
	<Order AmazonOrderId="012-0123456-0123456" SellerOrderId="" PurchaseDate="03/04/2014 10:30:55" LastUpdateDate="03/04/2014 11:01:13" OrderStatus="Unshipped" FulfillmentChannel="MFN" SalesChannel="Amazon.co.uk" OrderChannel="" ShipServiceLevel="Std UK Dom" NumberOfItemsShipped="0" NumberOfItemsUnshipped="1">
		<ShippingAddress Name="Zynk Software" AddressLine1="Nelson House" AddressLine2="Fleming Business Centre" AddressLine3="Jesmond" City="Newcastle" County="" District="" StateOrRegion="England" PostalCode="NE2 3AE" CountryCode="GB" Phone="0845 123 2920" />
		<OrderTotal CurrencyCode="GBP" Amount="10.29" />
		<OrderItems>
			<OrderItem ASIN="B00272N8Q2" SellerSKU="PROD001" Title="Test Product" QuantityOrdered="1" QuantityShipped="0" GiftMessageText="">
				<ItemPrice CurrencyCode="GBP" Amount="6.34" />
				<ShippingPrice CurrencyCode="GBP" Amount="3.95" />
				<GiftWrapPrice CurrencyCode="GBP" Amount="0.00" />
				<ItemTax CurrencyCode="GBP" Amount="0.00" />
				<ShippingTax CurrencyCode="GBP" Amount="0.00" />
				<GiftWrapTax CurrencyCode="GBP" Amount="0.00" />
				<ShippingDiscount CurrencyCode="GBP" Amount="0.00" />
				<PromotionDiscount CurrencyCode="GBP" Amount="0.00" />
			</OrderItem>
		</OrderItems>
	</Order>
</Orders>
```