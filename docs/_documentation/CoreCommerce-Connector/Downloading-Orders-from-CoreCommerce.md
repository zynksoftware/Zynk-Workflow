---
slug: downloading-orders-from-corecommerce
redirect_from: "/article/188-downloading-orders-from-corecommerce"
title: Downloading Orders from CoreCommerce
---
This task will import download orders from CoreCommerce in the CoreCommerce XML format.

## Settings
### Connection
_Required_  
The CoreCommerce connection to use. See the [Connecting to CoreCommerce](connecting-to-corecommerce) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all orders, or false to only download new orders since the Download From date.

### Download From
_Optional_  
The rolling date to download new orders from. This setting is updated automatically each time the task runs, but is only used when Download All is set to false.

### Order Numbers
_Optional_  
Enter a list of specific order numbers to download. The list can be entered as either a comma separated list, or using the 'Use a list' option on the  Zynk Object form. If a list of order numbers is provided, this will override the Download All, Download From and Order Statuses settings.

### Order Statuses
_Optional_  
Enter a list of order statuses to filter the orders on. The following options are available:

* ORDER\_STATUS\_PENDING
* ORDER\_STATUS\_APPROVED
* ORDER\_STATUS\_PARTIALLY\_SHIPPED
* ORDER\_STATUS\_SHIPPED
* ORDER\_STATUS\_PROCESSING
* ORDER\_STATUS\_BACKORDER
* ORDER\_STATUS\_DECLINED
* ORDER\_STATUS\_REFUNDED
* ORDER\_STATUS\_RMA
* ORDER\_STATUS\_VOID
* ORDER\_STATUS\_PAID

### Output File
_Required_  
The file to save the downloaded orders to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Core Commerce to Sage 50 Integration](core-commerce-to-sage-50-integration) article.

Sample output file:
```xml
<?xml version="1.0"?>
<Response xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Action>ACTION_TYPE_ORDER_LIST</Action>
	<Status>SUCCESS_CODE</Status>
	<Code />
	<List length="1" possibleLength="1">
		<Order id="1">
			<Number>1407235155-177</Number>
			<CustomerId>d049d70366e85376fd5fe4f5c5abe3e6</CustomerId>
			<BillingAddress>
				<FirstName>Adam</FirstName>
				<LastName>W</LastName>
				<Address1>Flemming Business Centre</Address1>
				<Address2>Jesmond</Address2>
				<City>Newcastle</City>
				<State />
				<Zip>NE2 3AE</Zip>
				<Email>support@zynk.com</Email>
				<Company>Zynk</Company>
				<County />
				<Country />
			</BillingAddress>
			<ShippingAddress>
				<FirstName>Adam</FirstName>
				<LastName>W</LastName>
				<Address1>Flemming Business Centre</Address1>
				<Address2>Jesmond</Address2>
				<City>Newcastle</City>
				<State />
				<Zip>NE2 3AE</Zip>
				<Email>support@zynk.com</Email>
				<Company>Zynk</Company>
				<County />
				<Country />
			</ShippingAddress>
			<Phone />
			<Fax />
			<IpAddress />
			<CustomFields length="0" />
			<TransactionId />
			<ShippingService />
			<ShippingMethod />
			<TotalWeight>
				<Amount>1</Amount>
				<Units>KGS</Units>
			</TotalWeight>
			<ShippingWeight>
				<Amount>1.0000</Amount>
				<Units>KGS</Units>
			</ShippingWeight>
			<Payment>
				<PaymentMethod>PAYMENT_COD_TYPE</PaymentMethod>
			</Payment>
			<Items length="1">
				<Item>
					<Quantity>1</Quantity>
					<Sku>PROD001</Sku>
					<Vendor id="0" />
					<ProductId>8</ProductId>
					<Name>Test Product</Name>
					<Options length="0" />
					<Variants length="0" />
					<Status>ORDER_ITEM_STATUS_REGULAR</Status>
					<ShippedAmount>0</ShippedAmount>
					<Price>
						<Amount>10.00</Amount>
					</Price>
					<ExtraPrice>
						<Amount />
					</ExtraPrice>
					<Weight>
						<Amount>1</Amount>
						<Units>KGS</Units>
					</Weight>
					<Taxable>TRUE_VALUE</Taxable>
					<ProductCost>
						<Amount>0.00</Amount>
					</ProductCost>
					<OptionCost>
						<Amount>0.00</Amount>
					</OptionCost>
					<AddedToCart>
						<UnixTimeStamp>1407235310</UnixTimeStamp>
						<Day>05</Day>
						<Month>08</Month>
						<Year>2014</Year>
						<Hour>05</Hour>
						<Minute>41</Minute>
						<Second>50</Second>
					</AddedToCart>
					<ShipExempt>FALSE_VALUE</ShipExempt>
					<SubscriptionEligible>TRUE_VALUE</SubscriptionEligible>
				</Item>
			</Items>
			<SubTotal>
				<Amount>10</Amount>
			</SubTotal>
			<TaxRates length="0" />
			<Discount>
				<Amount>0.00</Amount>
			</Discount>
			<ShippingAndHandling>
				<Amount>0</Amount>
			</ShippingAndHandling>
			<GrandTotal>
				<Amount>10</Amount>
			</GrandTotal>
			<Status>ORDER_STATUS_PENDING</Status>
			<ShippingDate>
				<UnixTimeStamp>1407906000</UnixTimeStamp>
				<Day>13</Day>
				<Month>08</Month>
				<Year>2014</Year>
				<Hour>00</Hour>
				<Minute>00</Minute>
				<Second>00</Second>
			</ShippingDate>
			<TrackingElements length="0" />
			<Memo />
			<Note>notes</Note>
			<NoteToCustomer />
			<Affiliates length="0" />
			<CouponCode />
			<GiftCertificateCode />
			<ShippingInstructions />
			<GiftCertificateAmountPaid>
				<Amount>0</Amount>
			</GiftCertificateAmountPaid>
			<ShippingTaxable>FALSE_VALUE</ShippingTaxable>
			<OrderDate>
				<UnixTimeStamp>1407257458</UnixTimeStamp>
				<Day>05</Day>
				<Month>08</Month>
				<Year>2014</Year>
				<Hour>11</Hour>
				<Minute>50</Minute>
				<Second>58</Second>
			</OrderDate>
			<VatInclusive>FALSE_VALUE</VatInclusive>
			<RemoteHost />
			<GoogleFulfillmentStatus />
			<GoogleFinancialStatus />
			<ChargeAmount>
				<Amount>0.00</Amount>
			</ChargeAmount>
			<RefundAmount>
				<Amount>0.00</Amount>
			</RefundAmount>
			<RewardPointsEarned>0</RewardPointsEarned>
			<HasBeenReturned>FALSE_VALUE</HasBeenReturned>
			<AdminFile />
			<CreditAmount>
				<Amount>0.00</Amount>
			</CreditAmount>
			<RechargeRate>0</RechargeRate>
			<RechargeType />
			<Parent />
			<PaymentDate>
				<UnixTimeStamp />
				<Day>31</Day>
				<Month>12</Month>
				<Year>1969</Year>
				<Hour>18</Hour>
				<Minute>00</Minute>
				<Second>00</Second>
			</PaymentDate>
			<PaymentText />
			<StoneEdgeExported>FALSE_VALUE</StoneEdgeExported>
			<PaymentGatewayStatus />
			<PaymentGatewayType />
			<PointOfSale>FALSE_VALUE</PointOfSale>
			<Tendered>
				<Amount>10</Amount>
			</Tendered>
			<Change>
				<Amount>0.00</Amount>
			</Change>
			<PointOfSaleExported>FALSE_VALUE</PointOfSaleExported>
			<OrderCost>
				<Amount>0.00</Amount>
			</OrderCost>
			<Captured>
				<Amount>0.00</Amount>
			</Captured>
			<GatewayTransactionId2 />
			<Reauthorized>FALSE_VALUE</Reauthorized>
			<FreightShipping>
				<Amount>0.00</Amount>
			</FreightShipping>
			<TaxCalculatedAfterDiscounts>FALSE_VALUE</TaxCalculatedAfterDiscounts>
			<QuickbooksId />
			<QuickbooksSessionId />
			<AdminAttention>FALSE_VALUE</AdminAttention>
			<PricingGroupLocation id="">
				<Name />
			</PricingGroupLocation>
			<PricingGroupShipDate>
				<UnixTimeStamp />
				<Day>31</Day>
				<Month>12</Month>
				<Year>1969</Year>
				<Hour>18</Hour>
				<Minute>00</Minute>
				<Second>00</Second>
			</PricingGroupShipDate>
			<DazzleExported>N</DazzleExported>
			<CustomerString>d049d70366e85376fd5fe4f5c5abe3e6</CustomerString>
			<KeywordTerm />
			<KeywordDescription />
			<CouponDiscount>
				<Amount>0.00</Amount>
			</CouponDiscount>
			<CustomerTaxExempt>FALSE_VALUE</CustomerTaxExempt>
		</Order>
	</List>
</Response>
```