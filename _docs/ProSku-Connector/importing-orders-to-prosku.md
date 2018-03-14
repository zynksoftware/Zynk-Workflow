---
slug: importing-orders-to-prosku
redirect_from: "/article/importing-orders-to-prosku"
title: Uploading orders to ProSKU
---
This task will upload orders that are supplied in an XML format.

## Fields
The below fields in bold are required when creating a product.

### Order Level
* __order_reference__
* marshalling_zone
* order_date
* order_type

### Customer Level
* __delivery_name__
* notes

### Shipping Level
* company_name
* carrier_code
* service_code
* phone_number
* email
* address_line_1
* address_line_2
* address_line_3
* address_line_4
* post_code
* town
* delivery_date
* delivery_time

### Country Level
* country_name
* iso_2_code
* iso_3_code

### Line Level
* __product_code__
* __quantity__
* stock_status
* rotation_date
* batch
* pallet_ref

## Settings
### ProSKU Connection
_Required_  
The connection to ProSKU to use. See [Connecting to ProSKU](connecting-to-prosku) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file that you want to import in Zynk XML format.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file, for full documentation and samples see [ProSKU Orders XML](prosku-orders-xml):  
```xml
<?xml version="1.0" encoding="UTF-8"?>
<orders>
  <order>
    <order_reference>order_reference1</order_reference>
    <order_date>29/07/2016</order_date>
    <order_type>Sales</order_type>
    <customer>
      <delivery_name>name</delivery_name>
      <notes>notes</notes>
      <shipping>
        <company_name>company_name</company_name>
        <carrier_code>Example Courier Company</carrier_code>
        <service_code>same_day</service_code>
        <address_line_1>23, Address Line</address_line_1>
        <address_line_2>Address Line 2</address_line_2>
        <address_line_3>
        </address_line_3>
        <address_line_4>
        </address_line_4>
        <town>
        </town>
        <post_code>PO5 C0D</post_code>
        <phone_number>12345678</phone_number>
        <email>
        </email>
        <delivery_date>10/08/2016</delivery_date>
        <delivery_time>20:00</delivery_time>
        <country>
          <country_name>United Kingdom</country_name>
          <iso_2_code>GB</iso_2_code>
          <iso_3_code>GBR</iso_3_code>
        </country>
      </shipping>
    </customer>
    <order_lines>
      <line>
        <product_code>Phantom</product_code>
        <quantity>5</quantity>
        <stock_status>Good</stock_status>
        <rotation_date>
        </rotation_date>
        <batch>
        </batch>
        <pallet_ref>
        </pallet_ref>
      </line>
      <line>
        <product_code>0028B001AA</product_code>
        <quantity>5</quantity>
        <stock_status>Good</stock_status>
        <rotation_date>
        </rotation_date>
        <batch>
        </batch>
        <pallet_ref>
        </pallet_ref>
      </line>
    </order_lines>
  </order>
</orders>
```
