---
slug: downloading-orders-from-woocommerce
redirect_from: "/article/337-downloading-orders-from-woocommerce"
title: Downloading Orders from WooCommerce
---
This task will download orders taken on your WooCommerce store to an XML file.

We recommend configuring the task to download all orders of a particular status. Once the orders have been processed successfully, the [Uploading Orders to WooCommerce](uploading-orders-to-woocommerce) task can be used to change the order status in WooCommerce to prevent the same ones downloading again.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce) article if you require more information on how to create/manage connections.

### Download Meta Data
_Required_  
Set to true to download additional meta data for the orders. Defaults to false.

### Download Setting > Date Created
_Required_  
The date to download orders from when the task is set to download new orders. Updates automatically each time a order is downloaded.

### Download Setting > Date Modified
_Required_  
The date to download orders from when the task is set to download modified orders. Updates automatically each time a order is downloaded.

### Download Setting > Export Modified, New or All Records
_Required_  
Choose which orders should be downloaded from WooCommerce. The available options are:

* __Modified__ - Downloads updated orders since the date shown in the Date Modified setting.
* __New__ - Downloads new orders since the date shown in the Date Created setting.
* __All__ - Downloads all orders.

### Page Size
_Required_  
The number of orders to download per page. Increasing this value will speed up the download, but will consume more memory. Defaults to 10.

### Output File
_Required_  
The name of the XML file to export the orders to. Defaults to 'woo_commerce_orders.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderList>
  <orders>
    <order>
      <id>9</id>
      <created_at>2015-03-12T17:05:25</created_at>
      <updated_at>2015-03-25T17:00:00</updated_at>
      <order_number>9</order_number>
      <completed_at>2015-03-25T17:00:00</completed_at>
      <status>processing</status>
      <currency>GBP</currency>
      <total>8.00</total>
      <subtotal>8.00</subtotal>
      <total_line_items_quantity>1</total_line_items_quantity>
      <total_tax>0.00</total_tax>
      <total_shipping>0.00</total_shipping>
      <cart_tax>0.00</cart_tax>
      <shipping_tax>0.00</shipping_tax>
      <total_discount>0.00</total_discount>
      <shipping_methods>Free Shipping</shipping_methods>
      <payment_details>
        <method_id>cheque</method_id>
        <method_title>Cheque Payment</method_title>
        <paid>false</paid>
      </payment_details>
      <billing_address>
        <first_name>Adam</first_name>
        <last_name>Wardle</last_name>
        <company>Zynk Software Ltd</company>
        <address_1>Nelson House</address_1>
        <address_2 />
        <city>Jesmond</city>
        <state>Tyne & Wear</state>
        <postcode>NE2 3AE</postcode>
        <country>GB</country>
        <email>support@zynk.com</email>
        <phone>08451232920</phone>
      </billing_address>
      <shipping_address>
        <first_name>Adam</first_name>
        <last_name>Wardle</last_name>
        <company>Zynk Software Ltd</company>
        <address_1>Nelson House</address_1>
        <address_2 />
        <city>Jesmond</city>
        <state>Tyne & Wear</state>
        <postcode>NE2 3AE</postcode>
        <country>GB</country>
      </shipping_address>
      <note>Leave by the gate</note>
      <customer_ip>::1</customer_ip>
      <customer_user_agent>Mozilla/5.0 (Windows NT 6.3; WOW64; rv:36.0) Gecko/20100101 Firefox/36.0</customer_user_agent>
      <customer_id>1</customer_id>
      <view_order_url>https://localhost:8080/wordpress-4.1.1/my-account/view-order/9</view_order_url>
      <line_items>
        <line_item>
          <id>1</id>
          <subtotal>8.00</subtotal>
          <subtotal_tax>0.00</subtotal_tax>
          <total>8.00</total>
          <total_tax>0.00</total_tax>
          <price>8.00</price>
          <quantity>1</quantity>
          <name>Test</name>
          <product_id>8</product_id>
          <sku>ABC123</sku>
          <meta />
        </line_item>
      </line_items>
      <shipping_lines>
        <shipping_line>
          <id>2</id>
          <method_id>free_shipping</method_id>
          <method_title>Free Shipping</method_title>
          <total>0.00</total>
        </shipping_line>
      </shipping_lines>
      <customer>
        <id>1</id>
        <created_at>2015-03-11T16:54:11</created_at>
        <updated_at xsi:nil="true" />
        <email>support@zynk.com</email>
        <first_name>Adam</first_name>
        <last_name />
        <username>admin</username>
        <last_order_id>9</last_order_id>
        <last_order_date>2015-03-12T17:05:25</last_order_date>
        <orders_count>1</orders_count>
        <total_spent>8.00</total_spent>
        <avatar_url>https://secure.gravatar.com/avatar/ad516503a11cd5ca435acc9bb6523536?s=96</avatar_url>
        <billing_address>
          <first_name>Adam</first_name>
          <last_name>Wardle</last_name>
          <company>Zynk Software Ltd</company>
          <address_1>Nelson House</address_1>
          <address_2 />
          <city>Jesmond</city>
          <state>Tyne & Wear</state>
          <postcode>NE2 3AE</postcode>
          <country>GB</country>
          <email>support@zynk.com</email>
          <phone>08451232920</phone>
        </billing_address>
        <shipping_address>
          <first_name>Adam</first_name>
          <last_name>Wardle</last_name>
          <company>Zynk Software Ltd</company>
          <address_1>Nelson House</address_1>
          <address_2 />
          <city>Jesmond</city>
          <state>Tyne & Wear</state>
          <postcode>NE2 3AE</postcode>
          <country>GB</country>
        </shipping_address>
        <customer_meta>
          <nickname>admin</nickname>
          <first_name>Adam</first_name>
          <last_name />
          <description />
          <rich_editing>true</rich_editing>
          <comment_shortcuts>false</comment_shortcuts>
          <admin_color>fresh</admin_color>
          <use_ssl>0</use_ssl>
          <show_admin_bar_front>true</show_admin_bar_front>
          <wp_capabilities>
            <administrator>true</administrator>
          </wp_capabilities>
          <wp_user_level>10</wp_user_level>
          <dismissed_wp_pointers>wp360_locks,wp390_widgets,wp410_dfw</dismissed_wp_pointers>
          <show_welcome_panel>1</show_welcome_panel>
          <wp_dashboard_quick_press_last_post_id>10</wp_dashboard_quick_press_last_post_id>
          <billing_first_name>Adam</billing_first_name>
          <billing_last_name>Wardle</billing_last_name>
          <billing_company>Zynk Software Ltd</billing_company>
          <billing_address_1>Nelson House</billing_address_1>
          <billing_address_2 />
          <billing_city>Jesmond</billing_city>
          <billing_postcode>NE2 3AE</billing_postcode>
          <billing_country>GB</billing_country>
          <billing_state>Tyne & Wear</billing_state>
          <billing_phone>08451232920</billing_phone>
          <billing_email>support@zynk.com</billing_email>
          <shipping_first_name>Adam</shipping_first_name>
          <shipping_last_name>Wardle</shipping_last_name>
          <shipping_company>Zynk Software Ltd</shipping_company>
          <shipping_address_1>Nelson House</shipping_address_1>
          <shipping_address_2 />
          <shipping_city>Jesmond</shipping_city>
          <shipping_postcode>NE2 3AE</shipping_postcode>
          <shipping_country>GB</shipping_country>
          <shipping_state>Tyne & Wear</shipping_state>
          <woocommerce_api_consumer_key>ck_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</woocommerce_api_consumer_key>
          <woocommerce_api_consumer_secret>cs_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</woocommerce_api_consumer_secret>
          <woocommerce_api_key_permissions>read_write</woocommerce_api_key_permissions>
        </customer_meta>
      </customer>
    </order>
  </orders>
</OrderList>
```