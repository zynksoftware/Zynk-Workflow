---
slug: exporting-orders-from-woocommerce-v3
title: Exporting Orders from WooCommerce V3.0+
---
This task will export orders taken on your WooCommerce store to an XML file.

We recommend configuring the task to export all orders of a particular status. Once the orders have been processed successfully, the [Uploading Orders to WooCommerce](uploading-orders-to-woocommerce) task can be used to change the order status in WooCommerce to prevent the same ones exporting again.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce-v3) article if you require more information on how to create/manage connections.

### Export Customers
_Required_  
Set to true to export the customer information related to each order.

### Export Setting > Date Created
_Required_  
The date to export orders from when the task is set to export new records. Updates automatically each time a order is exported.

### Export Setting > Date Modified
_Required_  
The date to export orders from when the task is set to export modified records. Updates automatically each time a order is exported.

### Export Setting > Export Modified, New or All Records
_Required_  
Choose which orders should be exported from WooCommerce. The available options are:

* __Modified__ - Exports all orders then only outputs those updated since the date shown in the Date Modified setting. Using this option is likely to cause the task to take a long time to run and result in a large number of API requests.
* __New__ - Exports new orders since the date shown in the Date Created setting.
* __All__ - Exports all orders.

### Order Status
_Optional_  
The status to filter the order download on. Leave blank to download orders with any status.

### Page Size
_Required_  
The number of orders to export per page. Increasing this value will speed up the export, but will consume more memory. Defaults to 10.

### Record IDs
_Optional_  
Enter a comma separated list of IDs of specific records to export. This will override the Export Settings.

### Output File
_Required_  
The name of the XML file to export the orders to. Defaults to 'woo_commerce_export_orders.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <order>
    <id>9</id>
    <external_id>2414</external_id>
    <date_created>2017-05-24T15:50:53</date_created>
    <date_created_gmt>2017-05-24T14:50:53</date_created_gmt>
    <date_modified>2019-09-18T17:30:05</date_modified>
    <date_modified_gmt>2019-09-18T16:30:05</date_modified_gmt>
    <parent_id>0</parent_id>
    <number>20</number>
    <order_key>wc_order_59259dcdd2d84</order_key>
    <created_via>checkout</created_via>
    <version>3.7.0</version>
    <status>cancelled</status>
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
    <customer_ip_address>::1</customer_ip_address>
    <customer_user_agent>mozilla/5.0 (windows nt 10.0; wow64; rv:53.0) gecko/20100101 firefox/53.0</customer_user_agent>
    <customer_note />
    <billing>
      <first_name>Adam</first_name>
      <last_name>Wardle</last_name>
      <company>Zynk Software Ltd</company>
      <address_1>Nelson House</address_1>
      <address_2 />
      <city>Jesmond</city>
      <state>Tyne &amp; Wear</state>
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
    <payment_method>cheque</payment_method>
    <payment_method_title>Check payments</payment_method_title>
    <transaction_id />
    <date_paid xsi:nil="true" />
    <date_paid_gmt xsi:nil="true" />
    <date_completed xsi:nil="true" />
    <date_completed_gmt xsi:nil="true" />
    <cart_hash>238ce812c453f12e11a4a8ad632fe394</cart_hash>
    <meta_data>
      <meta>
        <id>386</id>
        <key>_shipping_method</key>
        <value>
          <item>flat_rate:1</item>
        </value>
      </meta>
    </meta_data>
    <line_items>
      <line_item>
        <id>5</id>
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
        <id>7</id>
        <rate_code>GB-VAT-1</rate_code>
        <rate_id>1</rate_id>
        <label>VAT</label>
        <compound>false</compound>
        <tax_total>4.00</tax_total>
        <shipping_tax_total>0.00</shipping_tax_total>
        <meta_data />
      </tax_line>
      <tax_line>
        <id>10</id>
        <rate_code />
        <rate_id>0</rate_id>
        <label>VAT</label>
        <compound>false</compound>
        <tax_total>0.00</tax_total>
        <shipping_tax_total>0.00</shipping_tax_total>
        <meta_data />
      </tax_line>
    </tax_lines>
    <shipping_lines>
      <shipping_line>
        <id>6</id>
        <method_title>Flat rate</method_title>
        <method_id>flat_rate</method_id>
        <total>0.00</total>
        <total_tax>0.00</total_tax>
        <taxes>
          <tax_line>
            <id>total</id>
            <compound xsi:nil="true" />
            <tax_total xsi:nil="true" />
            <shipping_tax_total xsi:nil="true" />
          </tax_line>
          <tax_line>
            <id>1</id>
            <compound xsi:nil="true" />
            <tax_total xsi:nil="true" />
            <shipping_tax_total xsi:nil="true" />
          </tax_line>
        </taxes>
        <meta_data>
          <meta>
            <id>42</id>
            <key>Items</key>
            <value>Test product &amp;times; 1</value>
          </meta>
        </meta_data>
      </shipping_line>
    </shipping_lines>
    <fee_lines />
    <coupon_lines />
    <refunds />
    <set_paid xsi:nil="true" />
  </order>
</orders>
```