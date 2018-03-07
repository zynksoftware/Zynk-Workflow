---
slug: importing-sales-orders-to-sage-200-online
redirect_from: "/article/importing-sales-orders-to-sage-200-online"
title: Importing Sales Orders To Sage 200 Online
---
This task will insert new sales orders into Sage 200 Online, from an XML file.

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

### Prevent Reprocessing
_Required_  
When set to true this will prevent another record with the same `<external_id>` as a previously uploaded record from being uploaded to Sage.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesOrders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrder>
    <external_id>5230</external_id>
    <document_date>2016-05-23T00:00:00</document_date>
    <customer_document_no>Order 123</customer_document_no>
    <use_invoice_address>false</use_invoice_address>
    <settlement_discount_days>0</settlement_discount_days>
    <settlement_discount_percent>0.00</settlement_discount_percent>
    <customer>
      <reference>ZYNK0001</reference>
    </customer>
    <delivery_address>
      <address_1>Nelson House</address_1>
      <address_2>Jesmond</address_2>
      <address_3 />
      <address_4 />
      <city>Newcaslte</city>
      <county>Tyne & Wear</county>
      <postcode>NE2 3AE</postcode>
      <address_country_code>
        <code>GB</code>
      </address_country_code>
    </delivery_address>
    <lines>
      <line>
        <line_number>1</line_number>
        <line_type>EnumLineTypeStandard</line_type>
        <description>Test Product</description>
        <line_quantity>4.0</line_quantity>
        <selling_unit_price>10.0</selling_unit_price>
        <unit_discount_percent>0.0</unit_discount_percent>
        <unit_discount_value>0.0</unit_discount_value>
        <show_on_customer_docs>true</show_on_customer_docs>
        <show_on_picking_list_type>Show</show_on_picking_list_type>
        <product>
          <code>TEST001</code>
        </product>
        <tax_code>
          <code>1</code>
        </tax_code>
      </line>
      <line>
        <line_number>2</line_number>
        <line_type>EnumLineTypeCharge</line_type>
        <code>CARR001</code>
        <description>Carriage charge</description>
        <line_quantity>1.0</line_quantity>
        <selling_unit_price>5.0</selling_unit_price>
        <unit_discount_percent>0.0</unit_discount_percent>
        <unit_discount_value>0.0</unit_discount_value>
        <show_on_customer_docs>true</show_on_customer_docs>
        <show_on_picking_list_type>Show</show_on_picking_list_type>
        <tax_code>
          <code>1</code>
        </tax_code>
      </line>
    </lines>
  </SalesOrder>
</SalesOrders>
```
