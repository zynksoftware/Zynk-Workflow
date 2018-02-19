---
slug: uploading-products-to-sage-one
redirect_from: "/article/817-upload-products"
title: Uploading Products to Sage One
---
The Import Products task will create new and update existing non-stock items in Sage One. The product data must be provided in the [Sage One Product XML](sage-one-product-xml) format.

See [Uploading Stock Items to Sage One](uploading-stock-items-to-sage-one) for importing stock items into Sage One.

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
A sample input file is shown below. See [Sage One Product XML](sage-one-product-xml) for full documentation of the XML.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <products>
    <product>
      <item_code>PENCILS</item_code>
      <description>50 Coloured Pencils</description>
      <sales_ledger_account>
        <nominal_code>4000</nominal_code>
      </sales_ledger_account>
      <purchase_ledger_account>
        <nominal_code>5000</nominal_code>
      </purchase_ledger_account>
    </product>
  </products>
</sage_one_company>
```