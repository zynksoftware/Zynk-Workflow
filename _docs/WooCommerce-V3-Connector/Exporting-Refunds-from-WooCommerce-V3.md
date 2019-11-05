---
slug: exporting-refunds-from-woocommerce-v3
title: Exporting Refunds from WooCommerce V3.0+
---
This task will export refunds from your WooCommerce store to an XML file.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce-v3) article if you require more information on how to create/manage connections.

### Export Customers
_Required_  
Set to true to export the customer information related to each order.

### Export Setting > Date Created
_Required_  
The date to export products from when the task is set to export new records. Updates automatically each time a product is exported.

### Export Setting > Date Modified
_Required_  
The date to export products from when the task is set to export modified records. Updates automatically each time a product is exported.

### Export Setting > Export Modified, New or All Records
_Required_  
Choose which products should be exported from WooCommerce. The available options are:

* __Modified__ - Exports updated products since the date shown in the Date Modified setting.
* __New__ - Exports new products since the date shown in the Date Created setting.
* __All__ - Exports all products.

### Page Size
_Required_  
The number of products to export per page. Increasing this value will speed up the export, but will consume more memory. Defaults to 10.

### Record IDs
_Optional_  
Enter a comma separated list of IDs of specific records to export. This will override the Export Settings.

### Refund Order Status
_Optional_  
The status to filter the order download on to return refunded orders. Defaults to 'refunded'.

### Output File
_Required_  
The name of the XML file to export the products to. Defaults to 'woo_commerce_export_refunds.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <order>
    <id>145</id>
    <date_created>2019-11-04T17:21:50</date_created>
    <date_created_gmt>2019-11-04T17:21:50</date_created_gmt>
    <date_modified>2019-11-04T17:25:59</date_modified>
    <date_modified_gmt>2019-11-04T17:25:59</date_modified_gmt>
    <parent_id>0</parent_id>
    <number>145</number>
    <order_key>wc_order_T0miCatc8jj6e</order_key>
    <created_via>admin</created_via>
    <version>3.7.0</version>
    <status>refunded</status>
    <currency>GBP</currency>
    <discount_total>0.00</discount_total>
    <discount_tax>0.00</discount_tax>
    <shipping_total>0.00</shipping_total>
    <shipping_tax>0.00</shipping_tax>
    <cart_tax>4.00</cart_tax>
    <total>24.00</total>
    <total_tax>4.00</total_tax>
    <prices_include_tax>false</prices_include_tax>
    <customer_id>2</customer_id>
    <customer_ip_address />
    <customer_user_agent />
    <customer_note />
    <billing>
      <first_name>Adam</first_name>
      <last_name>Wardle</last_name>
      <company>Zynk Software Ltd</company>
      <address_1>Nelson House</address_1>
      <address_2 />
      <city>Jesmond</city>
      <state>Tyne &amp Wear</state>
      <postcode>NE2 3AE</postcode>
      <country>GB</country>
      <email>support@zynk.com</email>
      <phone>08451232920</phone>
    </billing>
    <shipping>
      <first_name>Adam</first_name>
      <last_name>Wardle</last_name>
      <company>Zynk Software Ltd</company>
      <address_1>Nelson House</address_1>
      <address_2 />
      <city>Jesmond</city>
      <state>Tyne &amp; Wear</state>
      <postcode>NE2 3AE</postcode>
      <country>GB</country>
    </shipping>
    <payment_method />
    <payment_method_title />
    <transaction_id />
    <date_paid xsi:nil="true" />
    <date_paid_gmt xsi:nil="true" />
    <date_completed xsi:nil="true" />
    <date_completed_gmt xsi:nil="true" />
    <cart_hash />
    <meta_data />
    <line_items>
      <line_item>
        <id>11</id>
        <name>Test product</name>
        <product_id>8</product_id>
        <variation_id>0</variation_id>
        <quantity>1</quantity>
        <tax_class />
        <subtotal>20.00</subtotal>
        <subtotal_tax>4.00</subtotal_tax>
        <total>20.00</total>
        <total_tax>4.00</total_tax>
        <taxes>
          <tax_line>
            <id>1</id>
            <compound xsi:nil="true" />
            <tax_total xsi:nil="true" />
            <shipping_tax_total xsi:nil="true" />
          </tax_line>
        </taxes>
        <meta_data />
        <sku>TEST001</sku>
        <price>20</price>
      </line_item>
    </line_items>
    <tax_lines>
      <tax_line>
        <id>12</id>
        <rate_code>GB-VAT-1</rate_code>
        <rate_id>1</rate_id>
        <label>VAT</label>
        <compound>false</compound>
        <tax_total>4.00</tax_total>
        <shipping_tax_total>0.00</shipping_tax_total>
        <meta_data />
      </tax_line>
    </tax_lines>
    <shipping_lines />
    <fee_lines />
    <coupon_lines />
    <refunds>
      <refund>
        <id>146</id>
        <date_created>2019-11-04T17:25:46</date_created>
        <date_created_gmt>2019-11-04T17:25:46</date_created_gmt>
        <date_modified xsi:nil="true" />
        <date_modified_gmt xsi:nil="true" />
        <amount>24.00</amount>
        <reason>Product was damaged</reason>
        <meta_data />
        <line_items>
          <LineItem>
            <id>13</id>
            <name>Test product</name>
            <product_id>8</product_id>
            <variation_id>0</variation_id>
            <quantity>-1</quantity>
            <tax_class />
            <subtotal>-20.00</subtotal>
            <subtotal_tax>-4.00</subtotal_tax>
            <total>-20.00</total>
            <total_tax>-4.00</total_tax>
            <taxes>
              <tax_line>
                <id>1</id>
                <compound xsi:nil="true" />
                <tax_total xsi:nil="true" />
                <shipping_tax_total xsi:nil="true" />
              </tax_line>
            </taxes>
            <meta_data>
              <meta>
                <id>88</id>
                <key>_refunded_item_id</key>
                <value>11</value>
              </meta>
            </meta_data>
            <sku>TEST001</sku>
            <price>20</price>
          </LineItem>
        </line_items>
        <total xsi:nil="true" />
      </refund>
    </refunds>
    <set_paid xsi:nil="true" />
  </order>
</orders>
```