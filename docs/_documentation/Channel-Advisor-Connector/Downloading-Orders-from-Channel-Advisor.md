---
slug: downloading-orders-from-channel-advisor
redirect_from: "/article/181-downloading-orders-from-channel-advisor"
title: Downloading Orders from Channel Advisor
---
This task will download new and updated orders from Channel Advisor in XML format.

## Settings
### Connection
_Required_  
The Channel Advisor connection to use. See the [Connecting to Channel Advisor](connecting-to-channel-advisor) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the orders to.

### Checkout Status
_Required_  
Select the checkout status of orders to download.

### Client Order IDs
_Optional_  
Specify specific orders to download using a comma separated list of alphanumeric client order IDs.

### Date From
_Optional_  
The date to download new/updated orders from. Updates automatically when the task runs.

### Detail Level
_Required_  
Set the level of detail required for the orders downloaded. Choose from Low, Medium, High or Complete.

### Distribution Center Code
_Optional_  
Set the distribution center code of orders you want to download.

### Export State
_Required_  
Set the export state of orders you want to download. Choose from Not Exported, Exported or Unknown.

### Fulfilment Type
_Required_  
Set the fulfilment type of orders you want to download. Choose from All, External Only, Seller Only, Seller Ship Only, Seller Pickup Only, Seller Ship To Store Only or Seller Courier Only

### Order IDs
_Optional_  
Specify specific orders to download using a comma separated list of numeric order IDs.

### Order State
_Required_  
Set the order state of orders you want to download. Choose from Active, Archived or Cancelled.

### Payment Status
_Required_  
Set the payment status of orders you want to download. Choose from Cleared, Submitted, Not Submitted, Deposited, Failed or No Change.

### Refund Status
_Required_  
Set the refund status of orders you want to download. Choose from No Refunds, Order Level, Line Item Level, Order And Line Item Level or Failed Attempts Only.

### Shipping Status
_Required_  
Set the refund status of orders you want to download. Choose from Shipped, Unshipped, Pending Shipment, Partially Shipped or No Change.

### Start Date
_Optional_  
The initial start date of the order download. Any orders created before this date will not be downloaded, even if they are updated. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Channel Advisor to Sage 50 Integration](channel-advisor-to-sage-50-integration) article.

Sample output file, showing an order placed via Amazon:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfOrderResponseDetailComplete xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<OrderResponseDetailComplete>
		<NumberOfMatches xmlns="http://api.channeladvisor.com/datacontracts/orders">99</NumberOfMatches>
		<OrderTimeGMT xmlns="http://api.channeladvisor.com/datacontracts/orders">2014-06-07T16:00:47</OrderTimeGMT>
		<LastUpdateDate xmlns="http://api.channeladvisor.com/datacontracts/orders">2014-06-07T16:54:19.107</LastUpdateDate>
		<TotalOrderAmount xmlns="http://api.channeladvisor.com/datacontracts/orders">165.0000</TotalOrderAmount>
		<OrderState xmlns="http://api.channeladvisor.com/datacontracts/orders">Active</OrderState>
		<DateCancelledGMT xsi:nil="true" xmlns="http://api.channeladvisor.com/datacontracts/orders" />
		<OrderID xmlns="http://api.channeladvisor.com/datacontracts/orders">12345678</OrderID>
		<ClientOrderIdentifier xmlns="http://api.channeladvisor.com/datacontracts/orders">123-1234567-1234567</ClientOrderIdentifier>
		<SellerOrderID xmlns="http://api.channeladvisor.com/datacontracts/orders" />
		<OrderStatus xmlns="http://api.channeladvisor.com/datacontracts/orders">
			<CheckoutStatus>Completed</CheckoutStatus>
			<CheckoutDateGMT>2014-06-07T16:00:47</CheckoutDateGMT>
			<PaymentStatus>Cleared</PaymentStatus>
			<PaymentDateGMT>2014-06-07T16:00:47</PaymentDateGMT>
			<ShippingStatus>Unshipped</ShippingStatus>
			<ShippingDateGMT>1900-01-01T00:00:00</ShippingDateGMT>
			<OrderRefundStatus>NoRefunds</OrderRefundStatus>
		</OrderStatus>
		<ResellerID xmlns="http://api.channeladvisor.com/datacontracts/orders" />
		<BuyerEmailAddress xmlns="http://api.channeladvisor.com/datacontracts/orders">xxxxxxx@marketplace.amazon.co.uk</BuyerEmailAddress>
		<EmailOptIn xmlns="http://api.channeladvisor.com/datacontracts/orders">false</EmailOptIn>
		<PaymentInfo xmlns="http://api.channeladvisor.com/datacontracts/orders">
			<PaymentType>Amazon</PaymentType>
			<CreditCardLast4 />
			<PayPalID />
			<MerchantReferenceNumber />
			<PaymentTransactionID />
		</PaymentInfo>
		<ShippingInfo xmlns="http://api.channeladvisor.com/datacontracts/orders">
			<AddressLine1>Zynk Software, Fleming Business Centre</AddressLine1>
			<AddressLine2>Jesmond</AddressLine2>
			<City>Newcastle</City>
			<Region>001</Region>
			<RegionDescription>No Region Required</RegionDescription>
			<PostalCode>NE2 3AE</PostalCode>
			<CountryCode>GB</CountryCode>
			<CompanyName />
			<JobTitle />
			<Title />
			<FirstName>John</FirstName>
			<LastName>Smith</LastName>
			<Suffix />
			<PhoneNumberDay>0845 123 2920</PhoneNumberDay>
			<PhoneNumberEvening />
			<ShipmentList>
				<Shipment>
					<ShippingCarrier>Amazon Merchants@</ShippingCarrier>
					<ShippingClass>Standard</ShippingClass>
					<TrackingNumber />
				</Shipment>
			</ShipmentList>
			<ShippingInstructions />
			<EstimatedShipDate xsi:nil="true" />
			<DeliveryDate xsi:nil="true" />
		</ShippingInfo>
		<BillingInfo xmlns="http://api.channeladvisor.com/datacontracts/orders">
			<AddressLine1>Zynk Software, Fleming Business Centre</AddressLine1>
			<AddressLine2>Jesmond</AddressLine2>
			<City>Newcastle</City>
			<Region>001</Region>
			<RegionDescription>No Region Required</RegionDescription>
			<PostalCode>NE2 3AE</PostalCode>
			<CountryCode>GB</CountryCode>
			<CompanyName />
			<Title />
			<FirstName>John</FirstName>
			<LastName>Smith</LastName>
			<Suffix />
			<PhoneNumberDay>0845 123 2920</PhoneNumberDay>
			<PhoneNumberEvening />
		</BillingInfo>
		<FlagDescription xmlns="http://api.channeladvisor.com/datacontracts/orders" />
		<ShoppingCart xmlns="http://api.channeladvisor.com/datacontracts/orders">
			<CartID>12345678</CartID>
			<CheckoutSource>Unspecified</CheckoutSource>
			<VATTaxCalculationOption>VAT_INCLUSIVE</VATTaxCalculationOption>
			<VATShippingOption>Unspecified</VATShippingOption>
			<VATGiftWrapOption>Unspecified</VATGiftWrapOption>
			<LineItemSKUList>
				<OrderLineItemItem xsi:type="OrderLineItemItemResponse">
					<LineItemType>SKU</LineItemType>
					<UnitPrice>165.0000</UnitPrice>
					<LineItemID>17232180</LineItemID>
					<AllowNegativeQuantity>false</AllowNegativeQuantity>
					<Quantity>1</Quantity>
					<ItemSaleSource>AMAZON_UK</ItemSaleSource>
					<SKU>ABC-123</SKU>
					<Title>Rotary Mens Date Display Watch</Title>
					<BuyerUserID>xxxxxxx@marketplace.amazon.co.uk</BuyerUserID>
					<BuyerFeedbackRating>0</BuyerFeedbackRating>
					<SalesSourceID>12360083805230</SalesSourceID>
					<VATRate>0.2000</VATRate>
					<TaxCost>27.5000</TaxCost>
					<ShippingCost>0.0000</ShippingCost>
					<ShippingTaxCost>0.0000</ShippingTaxCost>
					<GiftWrapCost>0.0000</GiftWrapCost>
					<GiftWrapTaxCost>0.0000</GiftWrapTaxCost>
					<GiftMessage />
					<GiftWrapLevel />
					<RecyclingFee>0.0000</RecyclingFee>
					<FulfillmentType>Ship</FulfillmentType>
					<UnitWeight UnitOfMeasure="KG">0.4</UnitWeight>
					<WarehouseLocation />
					<UserName />
					<DistributionCenterCode>London</DistributionCenterCode>
					<IsExternallyFulfilled>false</IsExternallyFulfilled>
					<ItemSaleSourceTransactionID>12360083805230</ItemSaleSourceTransactionID>
				</OrderLineItemItem>
			</LineItemSKUList>
			<LineItemInvoiceList>
				<OrderLineItemInvoice>
					<LineItemType>SalesTax</LineItemType>
					<UnitPrice>27.5000</UnitPrice>
				</OrderLineItemInvoice>
				<OrderLineItemInvoice>
					<LineItemType>Shipping</LineItemType>
					<UnitPrice>0.0000</UnitPrice>
				</OrderLineItemInvoice>
				<OrderLineItemInvoice>
					<LineItemType>ShippingInsurance</LineItemType>
					<UnitPrice>0.0000</UnitPrice>
				</OrderLineItemInvoice>
				<OrderLineItemInvoice>
					<LineItemType>VATShipping</LineItemType>
					<UnitPrice>0.0000</UnitPrice>
				</OrderLineItemInvoice>
				<OrderLineItemInvoice>
					<LineItemType>GiftWrap</LineItemType>
					<UnitPrice>0.0000</UnitPrice>
				</OrderLineItemInvoice>
				<OrderLineItemInvoice>
					<LineItemType>VATGiftWrap</LineItemType>
					<UnitPrice>0.0000</UnitPrice>
				</OrderLineItemInvoice>
				<OrderLineItemInvoice>
					<LineItemType>RecyclingFee</LineItemType>
					<UnitPrice>0.0000</UnitPrice>
				</OrderLineItemInvoice>
			</LineItemInvoiceList>
			<LineItemPromoList>
				<OrderLineItemPromo>
					<LineItemType>Promotion</LineItemType>
					<UnitPrice>0.0000</UnitPrice>
					<PromoCode />
				</OrderLineItemPromo>
			</LineItemPromoList>
		</ShoppingCart>
		<CustomValueList xmlns="http://api.channeladvisor.com/datacontracts/orders" />
		<BuyerIpAddress xmlns="http://api.channeladvisor.com/datacontracts/orders" />
		<TransactionNotes xmlns="http://api.channeladvisor.com/datacontracts/orders" />
	</OrderResponseDetailComplete>
</ArrayOfOrderResponseDetailComplete>
```