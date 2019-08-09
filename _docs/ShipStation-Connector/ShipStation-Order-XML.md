---
slug: shipstation-order-xml
title: ShipStation Order XML
---
The [Import Orders](importing-orders-into-shipstation) task allows you to create new and update existing orders in ShipStation. Any fields not documented below are not supported by our import.

Sample import file showing the minimum info required to create an order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <OrderNumber>984543</OrderNumber>
    <OrderDate>2019-07-29T00:00:00</OrderDate>
    <OrderStatus>awaiting_shipment</OrderStatus>
    <BillTo>
      <Name>John Smith</Name>
    </BillTo>
    <ShipTo>
      <Name>John Smith</Name>
      <Street1>8 Newcastle Enterprise Centres</Street1>
      <Street2>6 Charlotte Square</Street2>
      <City>Newcastle Upon Tyne</City>
      <State>Tyne and Wear</State>
      <PostalCode>NE1 4XF</PostalCode>
      <Country>GB</Country>
      <Residential>false</Residential>
    </ShipTo>
    <Items>
      <OrderItem>
        <Sku>SAGE50</Sku>
        <Name>Sage 50 Pro</Name>
        <Quantity>1</Quantity>
        <UnitPrice>200.00</UnitPrice>
        <TaxAmount>40.00</TaxAmount>
      </OrderItem>
    </Items>
  </Order>
</Orders>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create an order. The whole structure of the schema is used below as a reference of where fields should be in the object model.

## Order Summary  
The following info can be specified in the Order Summary section of the order.

| ShipStation Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- | --- |
| - | OrderKey* | 123 | string | Optional |
| - | ExternalId* | 123 | string | Optional |
| Order # | OrderNumber | 123 | string | Required |
| Status | OrderStatus* | awaiting_shipment | enum | Required |
| Store | AdvancedOptions/StoreId | 1 | int | Optional |
| Order Date | OrderDate | 2019-01-01 | date | Required |
| Paid Date | PaymentDate | 2019-01-01 | date | Optional |
| Hold Until | HoldUntilDate | 2019-01-01 | date | Optional |
| Ship By | ShipByDate | 2019-01-01 | date | Optional |
| Shipping Paid | ShippingAmount | 0.00 | decimal | Optional |
| Tax Paid | TaxAmount | 20.00 | decimal | Optional |
| Total Paid | AmountPaid | 120.00 | decimal | Optional |
| Tags | TagIds/int | 1 | int | Optional |

*   OrderKey* - A unique identifier for the order. If an orderKey is not provided, ShipStation will create a new order and generate a unique OrderKey for that order. If it is provided, the task will either: create a new order if the provided OrderKey is not found, or, update the existing order if the OrderKey is found.
*   ExternalId* - Used internally by Zynk to track which orders have been processed. Must be provided for the 'Prevent Reprocessing' task setting to work.
*   OrderStatus* - Possible values: awaiting_payment, awaiting_shipment, shipped, on_hold, cancelled

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <OrderKey>123</OrderKey>
    <ExternalId>123</ExternalId>
    <OrderNumber>123</OrderNumber>
    <OrderStatus>awaiting_shipment</OrderStatus>
    <OrderDate>2019-01-01</OrderDate>
    <PaymentDate>2019-01-01</PaymentDate>
    <HoldUntilDate>2019-01-01</HoldUntilDate>
    <ShipByDate>2019-01-01</ShipByDate>
    <ShippingAmount>0.00</ShippingAmount>
    <TaxAmount>20.00</TaxAmount>
    <AmountPaid>120.00</AmountPaid>
    <AdvancedOptions>
      <StoreId>1</StoreId>
    </AdvancedOptions>
    <TagIds>
      <int>1</int>
    </TagIds>
  </Order>
</Orders>
```

## Buyer/Recipient Info  
The following info can be specified in the Buyer/Recipient Info section of the order.

| ShipStation Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- | --- |
| - | CustomerUsername* | ZynkSoftware | string | Optional |
| Sold To > Name | BillTo/Name | John Smith | string | Optional |
| Sold To > Company | BillTo/Company | Zynk Software Limited | string | Optional |
| Sold To > Phone | BillTo/Phone | 0191 303 7279 | string | Optional |
| Ship To > Name | ShipTo/Name | John Smith | string | Optional |
| Ship To > Company | ShipTo/Company | Zynk Software Limited | string | Optional |
| Ship To > Address Line 1 | ShipTo/Street1 | 8 Newcastle Enterprise Centres | string | Optional |
| Ship To > Address Line 2 | ShipTo/Street2 | 6 Charlotte Square | string | Optional |
| Ship To > City | ShipTo/City | Newcastle Upon Tyne | string | Optional |
| Ship To > State/Region | ShipTo/State | Tyne and Wear | string | Optional |
| Ship To > Postal Code | ShipTo/PostalCode | NE1 4XF | string | Optional |
| Ship To > Country | ShipTo/Country* | GB | string | Optional |
| Ship To > Phone | ShipTo/Phone | 0191 303 7279 | string | Optional |
| - | ShipTo/Residential | false | bool | Optional |
| Ship To > Email | CustomerEmail | support@zynk.com | string | Optional |

*   CustomerUsername* - This property needs to be defined in order to generate a customer profile.
*   ShipTo/Country* - The two letter ISO code is required.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <CustomerUsername>ZynkSoftware</CustomerUsername>
    <BillTo>
      <Name>John Smith</Name>
      <Company>Zynk Software Limited</Company>
      <Phone>0191 303 7279</Phone>
    </BillTo>
    <ShipTo>
      <Name>John Smith</Name>
      <Company>Zynk Software Limited</Company>
      <Street1>8 Newcastle Enterprise Centres</Street1>
      <Street2>6 Charlotte Square</Street2>
      <City>Newcastle Upon Tyne</City>
      <State>Tyne and Wear</State>
      <PostalCode>NE1 4XF</PostalCode>
      <Country>GB</Country>
      <Phone>0191 303 7279</Phone>
      <Residential>false</Residential>
    </ShipTo>
    <CustomerEmail>support@zynk.com</CustomerEmail>
  </Order>
</Orders>
```

## Order Items  
The following info can be specified in the Order Items section of the order.

| ShipStation Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- | --- |
| - | LineItemKey* | 1 | string | Optional |
| SKU | Sku | SAGE50 | string | Required |
| Name | Name | Sage 50 Pro | string | Optional |
| Qty | Quantity | 1 | int | Required |
| Unit £ | UnitPrice | 100.00 | decimal | Required |
| - | TaxAmount | 20.00 | decimal | Optional |
| - | ShippingAmount | 0.00 | decimal | Optional |
| - | Weight/Value | 28.5 | decimal | Optional |
| - | Weight/Units* | grams | enum | Optional |
| - | WarehouseLocation | Aisle 3, Shelf A, Bin 5 | string | Optional |
| - | FulfillmentSku | SAGE50 | string | Optional |
| - | Adjustment | false | string | Optional |
| - | ShipTo/Residential | false | bool | Optional |
| - | Upc | 123456789 | string | Optional |

*   LineItemKey* - Unique identifier for the line from the source system.
*   Weight/Units* - Possible values: pounds, ounces, grams
*   Adjustment* - Indicates that an item is a non-physical adjustment to the order (e.g. a discount or promotional code)

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <Items>
      <OrderItem>
        <LineItemKey>1</LineItemKey>
        <Sku>SAGE50</Sku>
        <Name>Sage 50 Pro</Name>
        <Quantity>1</Quantity>
        <UnitPrice>100.00</UnitPrice>
        <TaxAmount>20.00</TaxAmount>
        <ShippingAmount>0.00</ShippingAmount>
        <Weight>
          <Value>28.5</Value>
          <Units>grams</Units>
        </Weight>
        <WarehouseLocation>Aisle 3, Shelf A, Bin 5</WarehouseLocation>
        <FulfillmentSku>SAGE50</FulfillmentSku>
        <Adjustment>false</Adjustment>
        <Upc>123456789</Upc>
      </OrderItem>
    </Items>
  </Order>
</Orders>
```

## Order Notes  
The following info can be specified in the Order Notes section of the order.

| ShipStation Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- | --- |
| Customer | CustomerNotes | Customer order notes | string | Optional |
| Internal | InternalNotes | Internal order notes | string | Optional |
| This is a gift | Gift | true | bool | Optional |
| Gift message | GiftMessage | Happy Birthday | string | Optional |
| Custom Field 1 | AdvancedOptions/CustomField1 | Custom 1 | string | Optional |
| Custom Field 2 | AdvancedOptions/CustomField2 | Custom 2 | string | Optional |
| Custom Field 3 | AdvancedOptions/CustomField3 | Custom 3 | string | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <CustomerNotes>Customer order notes</CustomerNotes>
    <InternalNotes>Internal order notes</InternalNotes>
    <Gift>true</Gift>
    <GiftMessage>Happy Birthday</GiftMessage>
    <AdvancedOptions>
      <CustomField1>Custom 1</CustomField1>
      <CustomField2>Custom 2</CustomField2>
      <CustomField3>Custom 3</CustomField3>
    </AdvancedOptions>
  </Order>
</Orders>
```

## Shipping Info  
The following info can be specified in the Shipping Info section of the order.

| ShipStation Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- | --- |
| Requested | RequestedShippingService | Express delivery | string | Optional |
| Ship From | AdvancedOptions/WarehouseId | 123 | int | Optional |
| Weight > Value | Weight/Value | 28.5 | decimal | Optional |
| Weight > Unit | Weight/Units* | grams | enum | Optional |
| Service | CarrierCode | dhl | string | Optional |
| Service | ServiceCode | express_uk | string | Optional |
| Package | PackageCode | standard | string | Optional |
| Size > L | Dimensions/Length | 12.5 | decimal | Optional |
| Size > W | Dimensions/Width | 12.5 | decimal | Optional |
| Size > H | Dimensions/Height | 12.5 | decimal | Optional |
| Size > Unit | Dimensions/Units* | centimeters | enum | Optional |
| Confirm | Confirmation* | signature | enum | Optional |
| Insurance | InsuranceOptions/Provider* | carrier | enum | Optional |
| Delivery Time | ShipDate | 2019-01-01 | date | Optional |

*   Weight/Units* - Possible values: pounds, ounces, grams
*   Dimensions/Units* - Possible values: inches, centimeters
*   Confirmation* - Possible values: none, delivery, signature, adult_signature, direct_signature
*   InsuranceOptions/Provider* - Possible values: shipsurance, carrier, provider

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <RequestedShippingService>Express delivery</RequestedShippingService>
    <AdvancedOptions>
      <WarehouseId>123</WarehouseId>
    </AdvancedOptions>
    <Weight>
      <Value>28.5</Value>
      <Units>grams</Units>
    </Weight>
    <CarrierCode>dhl</CarrierCode>
    <ServiceCode>express_uk</ServiceCode>
    <PackageCode>standard</PackageCode>
    <Size>
      <Length>12.5</Length>
      <Width>12.5</Width>
      <Height>12.5</Height>
      <Unit>centimeters</Unit>
    </Size>
    <Confirmation>signature</Confirmation>
    <InsuranceOptions>
      <Provider>carrier</Provider>
    </InsuranceOptions>
    <ShipDate>2019-01-01</ShipDate>
  </Order>
</Orders>
```

## Other Shipping Options  
The following info can be specified in the Other Shipping Options section of the order.

| ShipStation Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- | --- |
| This order is non-machinable | AdvancedOptions/NonMachinable | true | bool | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <AdvancedOptions>
      <NonMachinable>true</NonMachinable>
    </AdvancedOptions>
  </Order>
</Orders>
```
