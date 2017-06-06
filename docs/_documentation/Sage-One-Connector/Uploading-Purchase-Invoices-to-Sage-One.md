---
slug: uploading-purchase-invoices-to-sage-one
redirect_from: "/article/847-upload-purchase-invoices"
title: Uploading Purchase Invoices to Sage One
---
This task will upload purchase invoices that are supplied in the [Sage One Purchase Invoice XML](sage-one-purchase-invoice-xml) format.

## Fields
The below fields in bold are required when creating a purchase invoice, the other fields are optional when creating and updating. Please note, when uploading Purchase Invoices you can match the invoice to a supplier based on the `ContactId` element or selecting from the 'Match Contacts On' setting. Also, if no match is found based on your criteria Zynk can automatically create a contact if you set the 'Auto Create Contact' setting to true.

If no `Id` element is provided in the XML, the Prevent Updates function will not work.

### Purchase Invoice Level

* __DueDate__
* ContactId
* ContactName
* Reference
* Notes
* PurchaseInvoiceDate

### Main Address Level

* Email
* Telephone
* Mobile

### Purchase Invoice Item Level

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
A sample input file is shown below. See [Sage One Purchase Invoice XML](sage-one-purchase-invoice-xml) for full documentation of the XML format.
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