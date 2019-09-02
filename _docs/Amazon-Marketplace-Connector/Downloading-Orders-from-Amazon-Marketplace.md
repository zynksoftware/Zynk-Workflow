---
slug: downloading-orders-from-amazon-marketplace
redirect_from: "/article/147-downloading-orders-from-amazon-marketplace"
title: Downloading Orders from Amazon Marketplace
---
This task will provide a list of updated orders in XML format from a specified Amazon MWS account.

## Amazon Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Channels
_Required_  
Choose at least one marketplace to send the XML feed to. For information about how Amazon handles feeds sent to multiple marketplaces, see [Using Multiple Marketplaces](http://docs.developer.amazonservices.com/en_UK/feeds/Feeds_EU_Global_Seller.html).

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

## Export Settings
### Export Date
_Required_  
The initial date to download orders from. Any orders placed before this date will not download, even if they are updated. This can be used to prevent orders which have already been handled manually from being downloaded.

### Export From
_Required_  
The rolling datse to download updated orders from per channel. This will automatically update each time the task runs. TIP: If you want to re-download old orders, change the Download From property

### Export To > Download To Date
_Optional_  
Download records up to this date, required if 'Download to Enabled' is enabled.

### Export To > Download To Enabled
_Required_  
Set to true to only download records up to a certain date, if disabled will download records up to the current date.

### Fulfilment Channel
_Required_  
The fulfilment channel of orders to download from Amazon. Choose whether to download orders fulfilled by Amazon (AFN), not fulfilled by Amazon (MFN) or all (All).
Defaults to all fulfilment channels.

### Order ID
_Optional_  
Optionally provide a specific order id to export singularly.

### Order Status
_Required_  
The status of when you want to download the order from Amazon. Choose from Pending, Unshipped, PartiallyShipped, Shipped, Cancelled or Unfulfillable.

### Output File
_Required_  
The name of the file to export the downloaded orders to.

## Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Amazon to Sage Integration article](amazon-to-sage-integration).

Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders>
	<Order AmazonOrderId="012-0123456-0123456" SellerOrderId="" MarketplaceId="A1F83G8C2ARO7P" BuyerEmail="a9cxt8kt21g8qzk@marketplace.amazon.co.uk" BuyerName="John Smith" OrderType="StandardOrder" OrderStatus="Shipped" FulfillmentChannel="MFN" SalesChannel="Amazon.co.uk" OrderChannel="" ShipServiceLevel="Std UK Dom_1" ShipmentServiceLevelCategory="Standard" ShippedByAmazonTFM="False" CbaDisplayableShippingLabel="" TFMShipmentStatus="" PurchaseDate="01/04/2019 21:02:28" LastUpdateDate="02/04/2019 08:38:45" EarliestShipDate="02/04/2019 00:00:00" LatestShipDate="02/04/2019 23:59:59" EarliestDeliveryDate="04/04/2019 00:00:00" LatestDeliveryDate="05/04/2019 23:59:59" NumberOfItemsShipped="1" NumberOfItemsUnshipped="0" PaymentMethod="Other">
		<ShippingAddress Name="Zynk Software" AddressLine1="Nelson House" AddressLine2="Fleming Business Centre" AddressLine3="Jesmond" City="Newcastle" County="" District="" StateOrRegion="England" PostalCode="NE2 3AE" CountryCode="GB" Phone="0845 123 2920" />
		<OrderTotal CurrencyCode="GBP" Amount="10.29" />
		<OrderItems>
			<OrderItem OrderItemId="12302045414568" ASIN="B00272N8Q2" SellerSKU="PROD001" Title="Test Product" QuantityOrdered="1" QuantityShipped="0" GiftMessageText="">
				<ItemPrice CurrencyCode="GBP" Amount="6.34" />
				<ShippingPrice CurrencyCode="GBP" Amount="3.95" />
				<GiftWrapPrice CurrencyCode="GBP" Amount="0.00" />
				<ItemTax CurrencyCode="GBP" Amount="0.00" />
				<ShippingTax CurrencyCode="GBP" Amount="0.00" />
				<GiftWrapTax CurrencyCode="GBP" Amount="0.00" />
				<ShippingDiscount CurrencyCode="GBP" Amount="0.00" />
				<PromotionDiscount CurrencyCode="GBP" Amount="0.00" />
				<PromotionIds />
			</OrderItem>
		</OrderItems>
	</Order>
</Orders>
```
