---
slug: sage-one-sales-invoice-xml
title: Sage One Sales Invoice XML
---
Upload Sales Invoices allows you to create new and update existing sales invoice records in Sage One. You can either provide a field in the XML and set up the task to match sales invoice records based on that field, or alternatively you can provide an Id node in your XML.  

Any Sage One fields not documented below are not supported with our uploads.   

Sample upload file for creating a sales invoice record in Sage One:

```xml
<?xml version="1.0"?>
<ArrayOfSalesInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesInvoice>
    <Id>12345</Id>
    <ContactName>Black Sabbath</ContactName>
    <DueDate>2016-06-20</DueDate>
    <Reference>12345</Reference>
    <SalesInvoiceDate>2016-06-14</SalesInvoiceDate>
    <MainAddress>
      <Address1>Ozzy House</Address1>
      <Address2>123 Ozzy Road</Address2>
      <Town>Birmingham</Town>
      <County>West Midlands</County>
      <Postcode>B13 2DR</Postcode>
      <Country>
        <Code>GB</Code>
      </Country>
      <Email>ozzy@sabbath.co.uk</Email>
      <Telephone>0845 123 2921</Telephone>
    </MainAddress>
    <DeliveryAddress>
      <Address1>Oz House</Address1>
      <Address2>123 Oz Road</Address2>
      <Town>Birmingham</Town>
      <County>West Midlands</County>
      <Postcode>B11 2TZ</Postcode>
      <Country>
        <Code>GB</Code>
      </Country>
    </DeliveryAddress>
    <SalesInvoiceItems>
      <Item>
        <Sku>TEST</Sku>
        <Name>TEST</Name>
        <Qty>2</Qty>
        <UnitPrice>8.33</UnitPrice>
        <UnitPriceIncludesTax>false</UnitPriceIncludesTax>
        <TaxRate>
          <Rate>20</Rate>
        </TaxRate>
        <LedgerAccount>
          <Name>Sales Type A</Name>
        </LedgerAccount>
      </Item>
    </SalesInvoiceItems>
    <Carriage>4.16</Carriage>
    <CarriageTaxRate>
      <Rate>20</Rate>
    </CarriageTaxRate>
  </SalesInvoice>
</ArrayOfSalesInvoice>
```

##  Account Details
The below information is in relation to the contact details of the invoice.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | ContactSageOneRecordId | 1234567 | string | Optional |
| - | ContactId | 1234567 | string  | Optional |
| Company / Name | ContactName | Black Sabbath | string | Optional |

## Invoice Details
The below information is in relation to the main invoice details.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | SageOneRecordId | 1234567 | string | Optional |
| - | Id | 1234567 | string  | Optional |
| Due Date | DueDate | 2016-06-20 | string | Required |
| Reference | Reference | 12345 | string | Optional |
| Invoice Date | SalesInvoiceDate | 2016-06-14  | string   | Optional  |

## Address Details
The below information is in relation to the address details. You are required to provide a main address.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| Street 1 | Address1 | Ozzy House | string | Optional |
| Street 2 | Address2 | 123 Ozzy Road | string | Optional |
| Town / City | Town | Birmingham | string | Optional |
| State / Province | County | West Midlands | string | Optional |
| Postal Code | Postcode | NE1 B13 2DR | string | Optional |
| Email | Email | ozzy@sabbath.co.uk | string | Optional |
| Telephone | Telephone | 0845 123 2921 | string | Optional |
| Mobile | Mobile | 0773 863 6049 | string | Optional |

## Item Details
The below information is in relation to the item details, Name, Qty and Price are always required.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | Sku | TEST | string | Optional |
| Description | Name | TEST | string | Required |
| Qty/Hrs | Qty | 2 | double | Required |
| Price/Rate | UnitPrice | 8.33 | double | Required |
| - | UnitPriceIncludesTax | false | boolean | Optional |
| VAT | TaxRate/Rate | 20 | double | Optional |
| - | LedgerAccount/Name | Sales Type A | string | Optional |

## Carriage Details

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| Carriage | Carriage | 4.16 | double | Optional |
| Carriage | CarriageTaxRate/Rate | TEST | string | Optional |