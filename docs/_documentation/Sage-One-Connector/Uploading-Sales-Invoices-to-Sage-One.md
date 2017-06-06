---
slug: uploading-sales-invoices-to-sage-one
redirect_from: "/article/822-upload-sales-invoices"
title: Uploading Sales Invoices to Sage One
---
This task will upload sales invoices that are supplied in the [Sage One Sales Invoice XML](sage-one-sales-invoice-xml) format.

## Fields

The below fields in bold are required when creating a sales invoice, the other fields are optional when creating and updating. Please note, when uploading Sales Invoices you can match the invoice to a customer based on the `ContactId` element in the XML or selecting from the 'Match Contacts On' setting on the task. Also, if not match is found based on your criteria Zynk can automatically create a contact if you set the 'Auto Create Contact' setting to true.

If no `Id` element is provided in the XML, the Prevent Updates function will not work.

### Sales Invoice Level

* __DueDate__
* __MainAddress__
* __Item/Name__
* __Item/Qty__
* __Item/UnitPrice__
* __Item/UnitDiscountPercentage__
* ContactId
* ContactName
* Reference
* Notes
* DeliveryAddress
* SalesInvoiceDate
* Carriage
* CarriageTaxRate

### Main Address Level

* Address1
* Address2
* Town
* County
* Postcode
* Country/Id
* Coutnry/Code
* Country/Name
* Email
* Telephone
* Mobile

### Delivery Address Level

* Address1
* Address2
* Town
* County
* Postcode
* Country/Id
* Coutnry/Code
* Country/Name

### Sales Invoice Item Level

* __Name__
* __Qty__
* __UnitPrice__
* Sku
* UnitPriceIncludesTax
* TaxRate/Id
* TaxRate/Rate
* LedgerAccount/Id
* LedgerAccount/Name

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Auto Create Contact
_Required_  
If no matching contact is found, automatically generate a new contact based on the data provided.

### Match Contacts On
_Required_  
If no 'CompanyId' node provided, match contacts based on this field. Either ContactName, Telephone, Email or Postcode.

### Fail File
_Required_  
The name of a file for “failed” imports to be sent to.

### Input File
_Required_  
The source file that you want to import in Zynk XML format.

### Success File
_Required_  
The name of a file for “successful” imports to be sent to.

### Default Ledger Account
_Optional_  
The ledger account to use when one is not supplied on the record in your input file.

### Default Product Code
_Optional_  
The product code to use when one is not supplied on the record in your input file.

### Default Tax Rate
_Required_  
The tax rate to use when one is not supplied on the record in your input file.

### Prices Include Tax
_Required_  
Set to true if the prices in your input file include tax.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage One Sales Invoice XML](sage-one-sales-invoice-xml) for full documentation of the XML format.
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