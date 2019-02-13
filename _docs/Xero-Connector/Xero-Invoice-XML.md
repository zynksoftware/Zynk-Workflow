---
slug: xero-invoice-xml
title: Xero Invoice XML
---
The Upsert Invoices task allows you to create new and update existing invoices and bills in Xero. We recommend that the ExternalId field be populated by the unique ID of the invoices from the source system, Zynk uses this field to track invoices already imported to prevent duplicates being created in Xero.  

Any Xero fields not documented below are not supported with our imports. Examples of where in the XML the fields should appear are shown in the samples below. 

Sample import file for creating or updating an invoice:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroInvoice>
  <XeroInvoice>
    <Id>4e566128-1270-4b2d-85fe-7bd4cdf255b2</Id>
    <ExternalId>79142</ExternalId>
    <Number>INV-0001</Number>
    <Contact>
      <Id>cea98f0f-af1a-4b23-ac1b-9584ba014dcb</Id>
      <ContactNumber>A1D001</ContactNumber>
    </Contact>
    <Type>AccountsReceivable</Type>
    <Status>Submitted</Status>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <Date>2015-04-29T00:00:00</Date>
    <DueDate>2015-05-31T00:00:00</DueDate>
    <CurrencyCode>GBP</CurrencyCode>
    <CurrencyRate>1.000000</CurrencyRate>
    <Reference>Test Invoice</Reference>
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
  </XeroInvoice>
</ArrayOfXeroInvoice>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the XML schema is used below as a reference of where fields should be in the object model.

## Matching Invoices
Any of the following fields can be used to match the invoices provided in the XML to existing invoices in Xero. If you intend to update existing invoices, at least one of these fields should be provided.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Invoice ID | Id | 4e566128-1270-4b2d-85fe-7bd4cdf255b2 | guid | - | Optional |
| - | ExternalId | 79142 | string | 255 | Optional | Zynk stores a mapping between Xero's invoice ID and the ExternalId, and will use this to look up the invoice ID. |
| Invoice # | Number | INV-0001 | string | 255 | Optional | If this field is not provided, and no matching invoice is found based on the Id or ExternalId, a new invoice will be created and Xero will auto-generate the invoice number based on your settings. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroInvoice>
  <XeroInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <Id>4e566128-1270-4b2d-85fe-7bd4cdf255b2</Id>
    <ExternalId>79142</ExternalId>
    <Number>INV-0001</Number>
  </XeroInvoice>
</ArrayOfXeroInvoice>
```

## Invoice Header
The following fields can be set on the invoice header.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | Type | AccountsReceivable | enum | - | Optional | Used to control whether the data is used to create an invoice or bill. Use 'AccountsReceivable' to create an invoice, or 'AccountsPayable' to create a bill. Will default to 'AccountsReceivable' if not specified. |
| To | Contact/Id | cea98f0f-af1a-4b23-ac1b-9584ba014dcb | guid | - | Dependant | Used to find the contact. Required if the contact number is not provided. |
| To | Contact/ContactNumber | A1D001 | string | 50 | Dependant | Used to find the contact. Required if the contact ID is not provided. |
| Date | Date | 2015-04-29T00:00:00 | date/time | - | Optional | The date should be provided in XSD format. If the Date is not provided, it will default to the current date based on the timezone setting of the organisation. |
| Due Date | DueDate | 2015-05-31T00:00:00 | date/time | - | Optional | The date should be provided in XSD format. If the DueDate is not provided, it will be set based on the contact's terms. |
| Invoice # | Number | INV-0001 | string | 255 | Optional | When creating an invoice, if this field is not provided and no matching invoice is found based on the Id or ExternalId, a new invoice will be created and Xero will auto-generate the invoice number based on your settings. If you do provide this field, the value must be unique. When creating a bill, the value provided will be used as the reference, and does not need to be unique. |
| Reference | Reference | Test Invoice | string | 255 | Optional | This element will be ignored when creating a bill. To set the reference, you must use the Number element instead. |
| Branding | BrandingThemeId | b99ac1d4-f527-42e5-8ec3-5a2f5b26c03e | guid | - | Optional |
| Currency | CurrencyCode | GBP | string | 3 | Optional | Use the three-letter ISO currency code. |
| Exchange Rate | CurrencyRate | 1.000000 | decimal | - | Optional | Used to control the exchange rate. Maximum 6 decimal places. Will default to the current exchange rate if not provided. |
| Amounts Are | LineAmountTypes | Exclusive | enum | - | Optional | Possible values are: Exclusive, Inclusive, NoTax. Defaults to Exclusive if not specified. |
| Status | Status | Submitted | enum | - | Optional | Possible values are: Draft, Submitted, Authorised, Deleted, Voided. Will default to Draft is not specified. The statuses that are valid to use depend on the current status of the invoice, see [Xero's documentation](https://developer.xero.com/documentation/api/invoices#status-codes) for more information. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroInvoice>
  <XeroInvoice>
    <Contact>
      <Id>cea98f0f-af1a-4b23-ac1b-9584ba014dcb</Id>
      <ContactNumber>A1D001</ContactNumber>
    </Contact>
    <Date>2015-04-29T00:00:00</Date>
    <DueDate>2015-05-31T00:00:00</DueDate>
    <Number>INV-0001</Number>
    <Reference>Test Invoice</Reference>
    <BrandingThemeId>b99ac1d4-f527-42e5-8ec3-5a2f5b26c03e</BrandingThemeId>
    <CurrencyCode>GBP</CurrencyCode>
    <CurrencyRate>1.000000</CurrencyRate>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <Status>Submitted</Status>
  </XeroInvoice>
</ArrayOfXeroInvoice>
```

## Invoice Items
The following fields can be set on the invoice items.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | LineItemId | 89575076-c07d-465c-bb9d-69a0b4d43384 | guid | - | Optional | The Xero generated identifier for a LineItem. If LineItemIDs are not included with line items when updating an existing invoice, the line items are deleted and recreated. |
| Item | ItemCode | BOARD001 | string | 30 | Optional | Used to find a matching item in Xero. |
| Description | Description | Whiteboard - Drywipe (900 x 1200) | string | 4000 | Dependant | A description is required to create an approved invoice. |
| Qty | Quantity | 1.0000 | decimal | - | Optional |
| Unit Price | UnitAmount | 20.0000 | decimal | - | Optional |
| Disc % | DiscountRate | 10 | decimal | - | Optional |
| Account | AccountCode | 4000 | string | 10 | Optional |
| Tax Rate | TaxType | NONE | string | - | Optional | Will default to the tax rate of the selected account if not specified. See [Xero's documentation](https://developer.xero.com/documentation/api/types#taxRates) for a list of valid tax types. |
| Amount | LineAmount | 20.00 | decimal | - | Optional | Represents the line amount before tax. Will be calculated as Quantity * UnitAmount * ((100 - DiscountRate)/100) if not provided. |
| - | TaxAmount | 0 | decimal | - | Optional | Can be used to override the tax amount if the value calculated based on the TaxType and LineAmount is not correct. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroInvoice>
  <XeroInvoice>
    <LineItems>
      <LineItem>
        <LineItemId>89575076-c07d-465c-bb9d-69a0b4d43384</LineItemId>
        <ItemCode>BOARD001</ItemCode>
        <Description>Whiteboard - Drywipe (900 x 1200)</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>20.0000</UnitAmount>
        <DiscountRate>0</DiscountRate>
        <AccountCode>4000</AccountCode>
        <TaxType>NONE</TaxType>
        <LineAmount>20.00</LineAmount>
        <TaxAmount>0.00</TaxAmount>
      </LineItem>
    </LineItems>
  </XeroInvoice>
</ArrayOfXeroInvoice>
```

## Attachments
You can attach up to 10 files to an invoice in Xero. If the same file name is provided as an attachment already on the invoice in Xero, the existing file will be overwritten.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | FilePath | C:\10388.png | string | - | Required | The path of the file to upload to Xero |
| Name | FileName | upload.png | string | - | Optional | Will default to the file name specified in the FilePath if not provided |
| Include with Invoice | IncludeOnline | false | bool | - | Optional | Only available for accounts receivable invoices, defaults to false |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroInvoice>
  <XeroInvoice>
    <Attachments>
      <Attachment>
        <FilePath>C:\10388.png</FilePath>
        <FileName>upload.png</FileName>
        <IncludeOnline>false</IncludeOnline>
      </Attachment>
    </Attachments>
  </XeroInvoice>
</ArrayOfXeroInvoice>
```
