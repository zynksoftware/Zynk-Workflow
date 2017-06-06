---
slug: downloading-sales-invoices-from-sage-one
redirect_from: "/article/856-download-sales-invoices"
title: Downloading Sales Invoices from Sage One
---
This task will download Sales Invoices from your instance of Sage One.

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
A sample output file is shown below. See [Sage One Sales Invoice XML](sage-one-sales-invoice-xml) for full documentaion of the XML format.
```xml
<?xml version="1.0"?>
<ArrayOfSalesInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesInvoice>
    <SageOneRecordId>15050524</SageOneRecordId>
    <ContactId>9153979</ContactId>
    <ContactName>Black Sabbath</ContactName>
    <InvoiceNumber>SI-33</InvoiceNumber>
    <Status>Unpaid</Status>
    <DueDate>2016-06-20T00:00:00+01:00</DueDate>
    <Reference>SALESINV123</Reference>
    <MainAddressString>Ozzy House, 123 Ozzy Road, Birmingham, West Midlands, B13 2DR</MainAddressString>
    <DeliveryAddressString>Ozzy House, 123 Ozzy Road, Birmingham, West Midlands, B13 2DR</DeliveryAddressString>
    <SalesInvoiceDate>0001-01-01T00:00:00</SalesInvoiceDate>
    <SalesInvoiceItems>
      <Item>
        <SageOneRecordId>17421591</SageOneRecordId>
        <Sku>TEST</Sku>
        <Name>TEST</Name>
        <Qty>2</Qty>
        <UnitPrice>6.94</UnitPrice>
        <UnitPriceIncludesTax>true</UnitPriceIncludesTax>
        <TaxRate>
          <SageOneRecordId>1</SageOneRecordId>
          <Errors />
          <Name>Standard 20.00%</Name>
          <Rate>20</Rate>
          <SubTaxRates />
        </TaxRate>
        <NetAmount>13.32</NetAmount>
        <TaxAmount>3.33</TaxAmount>
      </Item>
    </SalesInvoiceItems>
    <Carriage>4.16</Carriage>
    <CarriageTaxRate>
      <SageOneRecordId>1</SageOneRecordId>
      <Errors />
      <Name>Standard 20.00%</Name>
      <Rate>20</Rate>
      <SubTaxRates />
    </CarriageTaxRate>
    <SalesInvoicePayments />
  </SalesInvoice>
  <SalesInvoice>
    <SageOneRecordId>15051313</SageOneRecordId>
    <ContactId>9153979</ContactId>
    <ContactName>Black Sabbath</ContactName>
    <InvoiceNumber>SI-34</InvoiceNumber>
    <Status>Unpaid</Status>
    <DueDate>2016-06-20T00:00:00+01:00</DueDate>
    <Reference>SALESINV123</Reference>
    <MainAddressString>Ozzy House, 123 Ozzy Road, Birmingham, West Midlands, B13 2DR</MainAddressString>
    <DeliveryAddressString>Ozzy House, 123 Ozzy Road, Birmingham, West Midlands, B13 2DR</DeliveryAddressString>
    <SalesInvoiceDate>0001-01-01T00:00:00</SalesInvoiceDate>
    <SalesInvoiceItems>
      <Item>
        <SageOneRecordId>17422337</SageOneRecordId>
        <Sku>TEST</Sku>
        <Name>TEST</Name>
        <Qty>2</Qty>
        <UnitPrice>6.94</UnitPrice>
        <UnitPriceIncludesTax>true</UnitPriceIncludesTax>
        <TaxRate>
          <SageOneRecordId>1</SageOneRecordId>
          <Errors />
          <Name>Standard 20.00%</Name>
          <Rate>20</Rate>
          <SubTaxRates />
        </TaxRate>
        <NetAmount>13.32</NetAmount>
        <TaxAmount>3.33</TaxAmount>
      </Item>
    </SalesInvoiceItems>
    <Carriage>4.16</Carriage>
    <CarriageTaxRate>
      <SageOneRecordId>1</SageOneRecordId>
      <Errors />
      <Name>Standard 20.00%</Name>
      <Rate>20</Rate>
      <SubTaxRates />
    </CarriageTaxRate>
    <SalesInvoicePayments />
  </SalesInvoice>
</ArrayOfSalesInvoice>
```