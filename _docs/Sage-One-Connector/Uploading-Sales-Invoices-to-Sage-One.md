---
slug: uploading-sales-invoices-to-sage-one
redirect_from: "/article/822-upload-sales-invoices"
title: Uploading Sales Invoices to Sage One
---
The Import Sales Invoices task will create new and update existing sales invoices in Sage One. The sales invoice data must be provided in the [Sage One Sales Invoice XML](sage-one-sales-invoice-xml) format.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file that you want to import in Zynk XML format.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once. This will only work where an `external_id` is provided for a record in the input XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage One Sales Invoice XML](sage-one-sales-invoice-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <sales_invoices>
    <sales_invoice>
      <contact>
        <reference>ZYNK0001</reference>
      </contact>
      <main_address>
        <address_line_1>Zynk Software</address_line_1>
        <address_line_2>6-8 Charlotte Square</address_line_2>
        <city>Newcastle upon Tyne</city>
        <region>Tyne &amp; Wear</region>
        <postal_code>NE1 4XF</postal_code>
        <country>
          <id>GB</id>
        </country>
      </main_address>
      <invoice_lines>
        <invoice_line>
          <description>Free text item</description>
          <ledger_account>
            <nominal_code>4000</nominal_code>
          </ledger_account>
          <quantity>1</quantity>
          <unit_price>10</unit_price>
          <tax_rate>
            <id>GB_STANDARD</id>
          </tax_rate>
        </invoice_line>
      </invoice_lines>
    </sales_invoice>
  </sales_invoices>
</sage_one_company>
```