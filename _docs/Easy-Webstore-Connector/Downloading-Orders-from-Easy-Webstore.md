---
slug: downloading-orders-from-easy-webstore
redirect_from: "/article/206-downloading-orders-from-easy-webstore"
title: Downloading Orders from Easy Webstore
---
This task will download orders from you Easy Webstore site to an XML file in the format described below.

## Settings
### Connection
_Required_  
The Easy Webstore connection to use.  See the [Connecting to Easy Webstore](connecting-to-easy-webstore) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to TRUE to download all orders, or set to FALSE to download only orders which have been modified since the last time this task ran. This option defaults to FALSE.

### Order Status
_Required_  
Use this option to filter the results returned by the order status. Set to 'Any' to download orders regardless of their status, or choose a particular status from the list. Defaults to 'Payment\_Pending'.

### Output File
_Required_  
The XML file to save the results to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Easy Webstore to Sage 50 Integration](easy-webstore-to-sage-50-integration) article.

Example of output format:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <ExtensionData />
    <ID>2830252</ID>
    <AdditionalDetails>Customers IP address at checkout was: XXX.XXX.XXX.XXX
Order delivery address: Nelson House,Fleming Business Centre,Jesmond,Newcastle,Tyne & Wear,NE2 3AE,United Kingdom
Tracking message sent: Some Courier
</AdditionalDetails>
    <BillingAddress1>Nelson House</BillingAddress1>
    <BillingAddress2>Fleming Business Centre</BillingAddress2>
    <BillingAddress3>Jesmond</BillingAddress3>
    <BillingCountry>United Kingdom</BillingCountry>
    <BillingCounty>Tyne & Wear</BillingCounty>
    <BillingPostcode>NE2 3AE</BillingPostcode>
    <BillingTown>Newcastle</BillingTown>
    <CostOfItems>17033</CostOfItems>
    <CouponDiscount>417</CouponDiscount>
    <CustomerID>568904</CustomerID>
    <DeliveryAddress1>Nelson House</DeliveryAddress1>
    <DeliveryAddress2>Fleming Business Centre</DeliveryAddress2>
    <DeliveryAddress3>Jesmond</DeliveryAddress3>
    <DeliveryCountry>United Kingdom</DeliveryCountry>
    <DeliveryCounty>Tyne & Wear</DeliveryCounty>
    <DeliveryPostcode>NE2 3AE</DeliveryPostcode>
    <DeliveryTown>Newcastle</DeliveryTown>
    <DispatchedTimeStamp>2012-08-24T11:56:01.217</DispatchedTimeStamp>
    <OrderItems>
      <OrderItem>
        <ExtensionData />
        <ID>7939751</ID>
        <ItemPriceAtTimeOfOrder>2500</ItemPriceAtTimeOfOrder>
        <ItemTaxAtTimeOfOrder>500</ItemTaxAtTimeOfOrder>
        <Option />
        <OptionCode />
        <ProductCode>PROD001</ProductCode>
        <ProductID>1962364</ProductID>
        <Quantity>1</Quantity>
      </OrderItem>
      <OrderItem>
        <ExtensionData />
        <ID>7939753</ID>
        <ItemPriceAtTimeOfOrder>14533</ItemPriceAtTimeOfOrder>
        <ItemTaxAtTimeOfOrder>2907</ItemTaxAtTimeOfOrder>
        <Option />
        <OptionCode />
        <ProductCode>PROD002</ProductCode>
        <ProductID>1962374</ProductID>
        <Quantity>1</Quantity>
      </OrderItem>
    </OrderItems>
    <PaymentCollectedTimeStamp>2012-08-24T10:42:03.7</PaymentCollectedTimeStamp>
    <PaymentMethod>Cash_On_Delivery</PaymentMethod>
    <PendingTimeStamp>2012-08-23T11:18:36.823</PendingTimeStamp>
    <ShippingCost>0</ShippingCost>
    <ShippingMethod>
      <ExtensionData />
      <ID>26379</ID>
      <Name>Demo store shipping</Name>
    </ShippingMethod>
    <ShippingTax>0</ShippingTax>
    <Status>Dispatched</Status>
    <TotalPayable>16616</TotalPayable>
  </Order>
</ArrayOfOrder>
```