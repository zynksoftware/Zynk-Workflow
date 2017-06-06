---
slug: downloading-purchase-invoices-from-sage-one
redirect_from: "/article/855-download-purchase-invoices"
title: Downloading Purchase Invoices from Sage One
---
This task will download Purchase Invoices from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Download Type
_Required_  
Select All, New or Modified.

### Invoice Status
_Required_  
Only download invoices of this status.

### Record Id
_Optional_  
Optionally download a specific record by specifying the Sage One id.

### Output File
_Required_  
The file to save the downloaded records to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage One Purchase Invoice XML](sage-one-purchase-invoice-xml) for full documentaion of the XML format.
```xml
<?xml version="1.0"?>
<ArrayOfPurchaseInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseInvoice>
    <SageOneRecordId>15054950</SageOneRecordId>
    <ContactId>9133252</ContactId>
    <ContactName>The Spiders From Mars</ContactName>
    <Status>Unpaid</Status>
    <DueDate>2016-06-20T00:00:00+01:00</DueDate>
    <Reference>12345</Reference>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <PurchaseInvoiceDate>0001-01-01T00:00:00</PurchaseInvoiceDate>
    <PurchaseInvoiceItems>
      <Item>
        <SageOneRecordId>17425856</SageOneRecordId>
        <Sku>PURPLE01</Sku>
        <Name>Purple Haze.</Name>
        <Qty>1</Qty>
        <UnitPrice>8.325</UnitPrice>
        <UnitPriceIncludesTax>false</UnitPriceIncludesTax>
        <TaxRate>
          <SageOneRecordId>1</SageOneRecordId>
          <Errors />
          <Name>Standard 20.00%</Name>
          <Rate>20</Rate>
          <SubTaxRates />
        </TaxRate>
        <NetAmount>8.33</NetAmount>
        <TaxAmount>1.67</TaxAmount>
      </Item>
    </PurchaseInvoiceItems>
    <PurchaseInvoicePayments />
  </PurchaseInvoice>
  <PurchaseInvoice>
    <SageOneRecordId>14990639</SageOneRecordId>
    <ContactId>8762276</ContactId>
    <ContactName>The Jimi Hendrix Experience</ContactName>
    <Status>Unpaid</Status>
    <DueDate>2016-06-20T00:00:00+01:00</DueDate>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <PurchaseInvoiceDate>0001-01-01T00:00:00</PurchaseInvoiceDate>
    <PurchaseInvoiceItems>
      <Item>
        <SageOneRecordId>17338697</SageOneRecordId>
        <Sku>HIGHWAY61</Sku>
        <Name>Highway 61 Revisited.</Name>
        <Qty>1</Qty>
        <UnitPrice>8.325</UnitPrice>
        <UnitPriceIncludesTax>false</UnitPriceIncludesTax>
        <TaxRate>
          <SageOneRecordId>1</SageOneRecordId>
          <Errors />
          <Name>Standard 20.00%</Name>
          <Rate>20</Rate>
          <SubTaxRates />
        </TaxRate>
        <NetAmount>8.33</NetAmount>
        <TaxAmount>1.67</TaxAmount>
      </Item>
    </PurchaseInvoiceItems>
    <PurchaseInvoicePayments />
  </PurchaseInvoice>
</ArrayOfPurchaseInvoice>
```