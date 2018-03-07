---
slug: importing-prereceipts-to-prosku
redirect_from: "/article/importing-prereceipts-to-prosku"
title: Importing Pre Receipts to ProSKU
---
This task will import pre receipts to ProSKU that are supplied in an XML format. 

## Fields
The below fields in bold are required when importing a pre receipt, the other fields are optional.

### Prereceipt level

* __additional_ref__
* date_of_receipt
* marshalling_zone
* notes
* supplier_detail

### Line level

* __product_code__
* __quantity__  (if total_quantity not provided)
* __secondary_quantity__ (if product requires secondary unit of measure and total quantity not provided)
* __total_quantity__  (if quantity and secondary quantity not provided)
* pallet_ref
* __rotation_date__  (if product requires rotation)
* __batch_no__  (if product requires batch number)
* location
* stock_status
* __serial_numbers__ If product records serials on receipts

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to ProSKU](connecting-to-prosku) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [ProSKU Pre Receipts XML](prosku-pre-receipts-xml):  

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<pre_receipts>
    <pre_receipt>
        <additional_ref>AddRef1</additional_ref>
        <date_of_receipt>22/02/2016</date_of_receipt>
        <notes>receipt through api</notes>
        <supplier_detail>CON001</supplier_detail>
        <pre_receipt_lines>
            <line>
                <product_code>Phantom</product_code>
                <quantity>4</quantity>
                <pallet_ref></pallet_ref>
                <rotation_date>12/07</rotation_date>
                <batch_no>17</batch_no>
                <location></location>
                <stock_status></stock_status>
            </line>
        </pre_receipt_lines>
    </pre_receipt>
</pre_receipts>
```
