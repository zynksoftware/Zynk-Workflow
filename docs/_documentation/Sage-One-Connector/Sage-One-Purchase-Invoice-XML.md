---
slug: sage-one-purchase-invoice-xml
title: Sage One Purchase Invoice XML
---
Upload Purchase Invoices allows you to create new and update existing sales invoice records in Sage One. You can either provide a field in the XML and set up the task to match sales invoice records based on that field, or alternatively you can provide an Id node in your XML.

Any Sage One fields not documented below are not supported with our uploads. 

Sample upload file for creating a sales invoice record in Sage One:

```xml
<?xml version="1.0"?>
<ArrayOfPurchaseInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseInvoice>
    <Id>12345</Id>
    <ContactName>The Spiders From Mars</ContactName>
    <PurchaseInvoiceDate>2016-06-14</PurchaseInvoiceDate>
    <Reference>12345</Reference>
    <DueDate>2016-06-20</DueDate>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <MainAddress>
      <Email>spiders@bowie.com</Email>
      <Telephone>0191 291 1758</Telephone>
      <Postcode>NE4 5LD</Postcode>
    </MainAddress>
    <PurchaseInvoiceItems>
      <Item>
        <Sku>PURPLE01</Sku>
        <Name>Purple Haze.</Name>
        <Qty>1</Qty>
        <UnitPrice>9.99</UnitPrice>
        <UnitPriceIncludesTax>true</UnitPriceIncludesTax>
      </Item>
    </PurchaseInvoiceItems>
  </PurchaseInvoice>
</ArrayOfPurchaseInvoice>
```

## Account Details
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
| Invoice Date | PurchaseInvoiceDate | 2016-06-14  | string   | Optional  |

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