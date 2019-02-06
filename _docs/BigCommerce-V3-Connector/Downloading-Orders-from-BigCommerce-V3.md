---
slug: downloading-orders-from-bigcommerce-v3
title: Downloading Orders from BigCommerce V3
---
This task will download orders taken on your BigCommerce store to an XML file.

## Settings
### Connection
_Required_  
The BigCommerce connection to use.See the [Connecting to BigCommerce V3](connecting-to-bigcommerce-v3) article if you require more information on how to create/manage connections.

### Export Coupons
_Required_  
Set to true to include detailed coupon information in the output file.  Defaults to True.

### Export Settings > Date Created
_Required_  
When the 'Export Type' is set to New, only records created after this date will be downloaded.  The date will update automatically each time the task runs based on the data returned.

### Export Settings > Date Modified
_Required_  
When the 'Export Type' is set to Modified, only records updated after this date will be downloaded.  The date will update automatically each time the task runs based on the data returned.

### Export Settings > Export Type
_Required_  
Used to choose which records should be included in the download.  The available options are: -

 - **New** - Only records created since the task last ran will be downloaded
 - **Modified** - Only records created or updated since the task last ran will be downloaded
 - **All** - All records will be downloaded, regardless of whether or not they have been updated since the task last ran

### Export Shipping Addresses
_Required_  
Set to true to include detailed shipping address in the output file.  Defaults to True.

### Order Status
_Optional_  
The status of the orders to be downloaded. If not set orders at any status will be downloaded.  Use the dropdown menu to select the required status.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. orders.xml).

### Page Size
_Required_  
The number of records returned per page of the request.  Defaults to 50.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below showing an order for 'Zynk Software Limited'.  For detailed documentation on the fields please see the [BigCommerce Dev Center](https://developer.bigcommerce.com/api-reference/orders/orders-api/models/order).

```xml
<?xml version="1.0" encoding="utf-8"?>
<orders>
  <order>
    <id>104</id>
    <zynk_external_id />
    <date_created>2013-08-09T14:04:01+01:00</date_created>
    <date_modified>2013-08-09T14:06:20+01:00</date_modified>
    <customer_id>1</customer_id>
    <date_shipped xsi:nil="true" />
    <status_id>10</status_id>
    <status>Completed</status>
    <custom_status>Completed</custom_status>
    <subtotal_ex_tax>499.0000</subtotal_ex_tax>
    <subtotal_inc_tax>598.8000</subtotal_inc_tax>
    <subtotal_tax>99.8000</subtotal_tax>
    <base_shipping_cost>0.0000</base_shipping_cost>
    <shipping_cost_ex_tax>0.0000</shipping_cost_ex_tax>
    <shipping_cost_inc_tax>0.0000</shipping_cost_inc_tax>
    <shipping_cost_tax>0.0000</shipping_cost_tax>
    <shipping_cost_tax_class_id>2</shipping_cost_tax_class_id>
    <base_handling_cost>0.0000</base_handling_cost>
    <handling_cost_ex_tax>0.0000</handling_cost_ex_tax>
    <handling_cost_inc_tax>0.0000</handling_cost_inc_tax>
    <handling_cost_tax>0.0000</handling_cost_tax>
    <handling_cost_tax_class_id>2</handling_cost_tax_class_id>
    <base_wrapping_cost>0.0000</base_wrapping_cost>
    <wrapping_cost_ex_tax>0.0000</wrapping_cost_ex_tax>
    <wrapping_cost_inc_tax>0.0000</wrapping_cost_inc_tax>
    <wrapping_cost_tax>0.0000</wrapping_cost_tax>
    <wrapping_cost_tax_class_id>3</wrapping_cost_tax_class_id>
    <total_ex_tax>499.0000</total_ex_tax>
    <total_inc_tax>598.8000</total_inc_tax>
    <total_tax>99.8000</total_tax>
    <items_total>1</items_total>
    <items_shipped>0</items_shipped>
    <payment_method>Cash on Delivery</payment_method>
    <payment_provider_id xsi:nil="true" />
    <payment_status />
    <refunded_amount>0.0000</refunded_amount>
    <order_is_digital>false</order_is_digital>
    <store_credit_amount>0.0000</store_credit_amount>
    <gift_certificate_amount>0.0000</gift_certificate_amount>
    <ip_address>78.86.222.163</ip_address>
    <currency_id>1</currency_id>
    <currency_code>GBP</currency_code>
    <currency_exchange_rate>1.0000000000</currency_exchange_rate>
    <default_currency_id>1</default_currency_id>
    <default_currency_code>GBP</default_currency_code>
    <staff_notes />
    <customer_message />
    <discount_amount>0.0000</discount_amount>
    <coupon_discount>0.0000</coupon_discount>
    <shipping_address_count>1</shipping_address_count>
    <is_deleted>false</is_deleted>
    <is_email_opt_in>false</is_email_opt_in>
    <ebay_order_id>0</ebay_order_id>
    <billing_address>
      <id xsi:nil="true" />
      <first_name>Joe</first_name>
      <last_name>Harrison</last_name>
      <company>Zynk Software Limited</company>
      <street_1>6-8 Charlotte Square</street_1>
      <street_2>i6</street_2>
      <city>Newcastle upon-Tyne</city>
      <state>Tyne and Wear</state>
      <zip>NE1 4XF</zip>
      <country>United Kingdom</country>
      <country_iso2>GB</country_iso2>
      <phone>0845 123 2920</phone>
      <email>joe.harrison@zynk.com</email>
      <form_fields />
    </billing_address>
    <order_source>manual</order_source>
    <products>
      <resource>/orders/104/products</resource>
      <url>https://api.bigcommerce.com/stores/v5k4i/v2/orders/104/products</url>
      <records>
        <order_product>
          <id>6</id>
          <order_id>104</order_id>
          <product_id>186</product_id>
          <order_address_id>5</order_address_id>
          <name>iPhone 4 16GB White</name>
          <sku>IPHONE4</sku>
          <type>physical</type>
          <base_price>499.0000</base_price>
          <price_exc_tax xsi:nil="true" />
          <price_inc_tax>598.8000</price_inc_tax>
          <price_tax>99.8000</price_tax>
          <base_total>499.0000</base_total>
          <total_exc_tax xsi:nil="true" />
          <total_inc_tax>598.8000</total_inc_tax>
          <total_tax>99.8000</total_tax>
          <quantity>1</quantity>
          <base_cost_price>0.0000</base_cost_price>
          <cost_price_inc_tax>0.0000</cost_price_inc_tax>
          <cost_price_ex_tax>0.0000</cost_price_ex_tax>
          <weight>0.0000</weight>
          <width>0.0000</width>
          <depth>0.0000</depth>
          <height>0.0000</height>
          <cost_price_tax>0.0000</cost_price_tax>
          <is_refunded>false</is_refunded>
          <refunded_amount xsi:nil="true" />
          <return_id>0</return_id>
          <wrapping_name />
          <base_wrapping_cost>0.0000</base_wrapping_cost>
          <wrapping_cost_ex_tax>0.0000</wrapping_cost_ex_tax>
          <wrapping_cost_inc_tax>0.0000</wrapping_cost_inc_tax>
          <wrapping_message />
          <quantity_shipped>0</quantity_shipped>
          <event_date xsi:nil="true" />
          <fixed_shipping_cost>0.0000</fixed_shipping_cost>
          <ebay_item_id />
          <ebay_transaction_id />
          <option_set_id xsi:nil="true" />
          <parent_order_product_id xsi:nil="true" />
          <is_bundled_product>false</is_bundled_product>
          <bin_picking_number />
          <applied_discounts />
          <product_options />
          <external_id xsi:nil="true" />
        </order_product>
      </records>
    </products>
    <shipping_addresses>
      <resource>/orders/104/shippingaddresses</resource>
      <url>https://api.bigcommerce.com/stores/v5k4i/v2/orders/104/shippingaddresses</url>
      <records>
        <address>
          <id>5</id>
          <first_name>Joe</first_name>
          <last_name>Harrison</last_name>
          <company>Zynk Software Limited</company>
          <street_1>6-8 Charlotte Square</street_1>
          <street_2>i6</street_2>
          <city>Newcastle upon-Tyne</city>
          <state>Tyne and Wear</state>
          <zip>NE1 4XF</zip>
          <country>United Kingdom</country>
          <country_iso2>GB</country_iso2>
          <phone>0845 123 2920</phone>
          <email />
          <form_fields />
        </address>
      </records>
    </shipping_addresses>
    <coupons>
      <resource>/orders/104/coupons</resource>
      <url>https://api.bigcommerce.com/stores/v5k4i/v2/orders/104/coupons</url>
    </coupons>
    <channel_id>1</channel_id>
    <tax_provider_id />
  </order>
</orders>
```