---
slug: xero-purchase-order-xml
title: Xero Purchase Order XML
---
The Upsert Purchase Orders task allows you to create new and update existing purchase orders in Xero. We recommend that the ExternalId field be populated by the unique ID of the purchase orders from the source system, Zynk uses this field to track purchase orders already imported to prevent duplicates being created in Xero.  

Any Xero fields not documented below are not supported with our imports. Examples of where in the XML the fields should appear are shown in the samples below. 

Sample import file for creating or updating a purchase order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder>
  <XeroPurchaseOrder>
    <Id>e9228aac-745b-4d05-b121-31c98b6593fc</Id>
    <ExternalId>79142</ExternalId>
    <Number>PO-0003</Number>
    <Contact>
      <Id>20435ce7-50b7-4a86-926a-8248778e1dcb</Id>
      <ContactNumber>CON001</ContactNumber>
    </Contact>
    <Status>Submitted</Status>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <Date>2015-04-29T00:00:00</Date>
    <DeliveryDate>2015-05-31T00:00:00</DeliveryDate>
    <CurrencyCode>GBP</CurrencyCode>
    <DeliveryAddress>Newcastle Enterprise Centres
6 Charlotte Square
Newcastle upon Tyne
Tyne and Wear
NE1 4XF
United Kingdom</DeliveryAddress>
    <AttentionTo>Bob</AttentionTo>
    <Telephone>0191 303 7279</Telephone>
    <DeliveryInstructions>Leave by the gate</DeliveryInstructions>
    <CurrencyRate>1.000000</CurrencyRate>
    <Reference>Test Purchase Order</Reference>
    <LineItems>
      <LineItem>
        <LineItemId>89575076-c07d-465c-bb9d-69a0b4d43384</LineItemId>
        <Description>Whiteboard - Drywipe (900 x 1200)</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>20.0000</UnitAmount>
        <AccountCode>4000</AccountCode>
        <ItemCode>BOARD001</ItemCode>
        <TaxType>NONE</TaxType>
        <TaxAmount>0.00</TaxAmount>
        <LineAmount>20.00</LineAmount>
        <DiscountRate>0</DiscountRate>
        <Tracking />
      </LineItem>
    </LineItems>
  </XeroPurchaseOrder>
</ArrayOfPurchaseOrder>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the XML schema is used below as a reference of where fields should be in the object model.

## Matching Purchase Orders
Any of the following fields can be used to match the purchase orders provided in the XML to existing purchase orders in Xero. If you intend to update existing purchase orders, at least one of these fields should be provided.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Purchase Order ID | Id | e9228aac-745b-4d05-b121-31c98b6593fc | guid | - | Optional |
| - | ExternalId | 79142 | string | 255 | Optional | Zynk stores a mapping between Xero's purchase order ID and the ExternalId, and will use this to look up the purchase order ID. |
| Order Number | Number | PO-0003 | string | 255 | Optional | If this field is not provided, and no matching invoice is found based on the Id or ExternalId, a new invoice will be created and Xero will auto-generate the purchase order number based on your settings. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder>
  <XeroPurchaseOrder>
    <Id>e9228aac-745b-4d05-b121-31c98b6593fc</Id>
    <ExternalId>79142</ExternalId>
    <Number>PO-0003</Number>
  </XeroPurchaseOrder>
</ArrayOfPurchaseOrder>
```

## Purchase Order Header
The following fields can be set on the purchase order header.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Contact | Contact/Id | 20435ce7-50b7-4a86-926a-8248778e1dcb | guid | - | Dependant | Used to find the contact. Required if the contact number is not provided. |
| Contact | Contact/ContactNumber | CON001 | string | 50 | Dependant | Used to find the contact. Required if the contact ID is not provided. |
| Date | Date | 2015-04-29T00:00:00 | date/time | - | Optional | The date should be provided in XSD format. If the Date is not provided, it will default to the current date based on the timezone setting of the organisation. |
| Delivery Date | DeliveryDate | 2015-05-31T00:00:00 | date/time | - | Optional | The date should be provided in XSD format. |
| Order number | Number | INV-0001 | string | 255 | Optional | If this field is not provided, and no matching purchase order is found based on the Id or ExternalId, a new purchase order will be created and Xero will auto-generate the order number based on your settings. |
| Reference | Reference | Test Invoice | string | 255 | Optional |
| Theme | BrandingThemeID | b99ac1d4-f527-42e5-8ec3-5a2f5b26c03e | guid | - | Optional |
| Currency | CurrencyCode | GBP | string | 3 | Optional | Use the three-letter ISO currency code. |
| Exchange Rate | CurrencyRate | 1.000000 | decimal | - | Optional | Used to control the exchange rate. Maximum 6 decimal places. Will default to the current exchange rate if not provided. |
| Amounts Are | LineAmountTypes | Exclusive | enum | - | Optional | Possible values are: Exclusive, Inclusive, NoTax. Defaults to Exclusive if not specified. |
| Status | Status | Submitted | enum | - | Optional | Possible values are: Draft, Submitted, Authorised, Deleted. Will default to Draft is not specified. The statuses that are valid to use depend on the current status of the invoice, see [Xero's documentation](https://developer.xero.com/documentation/api/types#purchaseorderstatuses) for more information. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder>
  <XeroPurchaseOrder>
    <Contact>
      <Id>20435ce7-50b7-4a86-926a-8248778e1dcb</Id>
      <ContactNumber>CON001</ContactNumber>
    </Contact>
    <Date>2015-04-29T00:00:00</Date>
    <DeliveryDate>2015-05-31T00:00:00</DeliveryDate>
    <Number>PO-0003</Number>
    <Reference>Test Purchase Order</Reference>
    <BrandingThemeID>b99ac1d4-f527-42e5-8ec3-5a2f5b26c03e</BrandingThemeID>
    <CurrencyCode>GBP</CurrencyCode>
    <CurrencyRate>1.000000</CurrencyRate>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <Status>Submitted</Status>
  </XeroPurchaseOrder>
</ArrayOfPurchaseOrder>
```

## Purchase Order Items
At least one item line is required to create a purchase order. The following fields can be set on the purchase order items.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | LineItemId | 89575076-c07d-465c-bb9d-69a0b4d43384 | guid | - | Optional | The Xero generated identifier for a LineItem. If LineItemIDs are not included with line items when updating an existing purchase order, the line items are deleted and recreated. |
| Item | ItemCode | BOARD001 | string | 30 | Optional | Used to find a matching item in Xero. |
| Description | Description | Whiteboard - Drywipe (900 x 1200) | string | 4000 | Dependant | A description is required to create an approved purchase order. |
| Qty | Quantity | 1.0000 | decimal | - | Optional |
| Unit Price | UnitAmount | 20.0000 | decimal | - | Optional |
| Disc % | DiscountRate | 10 | decimal | - | Optional |
| Account | AccountCode | 4000 | string | 10 | Optional |
| Tax Rate | TaxType | NONE | string | - | Optional | Will default to the tax rate of the selected account if not specified. See [Xero's documentation](https://developer.xero.com/documentation/api/types#taxRates) for a list of valid tax types. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder>
  <XeroPurchaseOrder>
    <LineItems>
      <LineItem>
        <LineItemId>89575076-c07d-465c-bb9d-69a0b4d43384</LineItemId>
        <Description>Whiteboard - Drywipe (900 x 1200)</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>20.0000</UnitAmount>
        <AccountCode>4000</AccountCode>
        <ItemCode>BOARD001</ItemCode>
        <TaxType>NONE</TaxType>
        <TaxAmount>0.00</TaxAmount>
        <LineAmount>20.00</LineAmount>
        <DiscountRate>0</DiscountRate>
        <Tracking />
      </LineItem>
    </LineItems>
  </XeroPurchaseOrder>
</ArrayOfPurchaseOrder>
```

## Purchase Order Footer
The following fields can be set on the purchase order footer.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Delivery Address | DeliveryAddress | Newcastle Enterprise Centres 6 Charlotte Square Newcastle upon Tyne Tyne and Wear NE1 4XF United Kingdom | string | 500 | Optional |
| Attention | AttentionTo | Bob | string | 50 | Optional |
| Telephone | Telephone | 0191 303 7279 | string | 50 | Optional |
| Delivery Instructions | DeliveryInstructions | Leave by the gate | string | 500 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder>
  <XeroPurchaseOrder>
    <DeliveryAddress>Newcastle Enterprise Centres
6 Charlotte Square
Newcastle upon Tyne
Tyne and Wear
NE1 4XF
United Kingdom</DeliveryAddress>
    <AttentionTo>Bob</AttentionTo>
    <Telephone>0191 303 7279</Telephone>
    <DeliveryInstructions>Leave by the gate</DeliveryInstructions>
  </XeroPurchaseOrder>
</ArrayOfPurchaseOrder>
```