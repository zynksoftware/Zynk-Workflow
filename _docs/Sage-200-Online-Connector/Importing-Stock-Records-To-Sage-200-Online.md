---
slug: importing-stock-records-to-sage-200-online
redirect_from: "/article/importing-stock-records-to-sage-200-online"
title: Importing Stock Records To Sage 200 Online
---
This task will insert new stock records in Sage 200 Online, using [Sage 200 Online Stock Record XML](sage-200-online-stock-record-xml) format.

Please note that all new products created by this task must have at least one location specified.

## Settings
### Sage 200 Online Connection
_Required_  
The connection to Sage 200 Online to use. See the [Connecting to Sage 200 Online](connecting-to-sage-200-online) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
 The XML file to output any records to which fail to upload to Sage.

### Input File
_Required_  
The XML file containing the records to upload to Sage. See below for a sample input file.

### Success File
_Required_  
The XML file to output any records to which are successfully uploaded to Sage.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Products xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <external_id>41241</external_id>
    <code>TEST003</code>
    <name>Test Product</name>
    <description>This is a test product</description>
    <barcode>124124142</barcode>
    <allow_sales_order>true</allow_sales_order>
    <tax_code>
      <code>1</code>
    </tax_code>
    <product_group>
      <code>GROUP01</code>
    </product_group>
  </Product>
</Products>
```
