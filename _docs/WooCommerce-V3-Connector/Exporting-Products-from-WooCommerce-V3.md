---
slug: exporting-products-from-woocommerce-v3
title: Exporting Products from WooCommerce V3.0+
---
This task will export products from your WooCommerce store to an XML file.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce-v3) article if you require more information on how to create/manage connections.

### Export Setting > Date Created
_Required_  
The date to export products from when the task is set to export new records. Updates automatically each time a product is exported.

### Export Setting > Date Modified
_Required_  
The date to export products from when the task is set to export modified records. Updates automatically each time a product is exported.

### Export Setting > Export Modified, New or All Records
_Required_  
Choose which products should be exported from WooCommerce. The available options are:

* __Modified__ - Exports all products then only outputs those updated since the date shown in the Date Modified setting. Using this option is likely to cause the task to take a long time to run and result in a large number of API requests.
* __New__ - Exports new products since the date shown in the Date Created setting.
* __All__ - Exports all products.

### Page Size
_Required_  
The number of products to export per page. Increasing this value will speed up the export, but will consume more memory. Defaults to 10.

### Record IDs
_Optional_  
Enter a comma separated list of IDs of specific records to export. This will override the Export Settings.

### Output File
_Required_  
The name of the XML file to export the products to. Defaults to 'woo_commerce_products.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<products xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <product>
    <id>8</id>
    <date_created>2017-05-22T16:37:29</date_created>
    <date_created_gmt>2017-05-22T15:37:29</date_created_gmt>
    <date_modified>2019-09-18T14:42:12</date_modified>
    <date_modified_gmt>2019-09-18T13:42:12</date_modified_gmt>
    <name>Test product</name>
    <slug>test-product</slug>
    <permalink>http://cerulean:8080/wordpress-no-ssl/product/test-product/</permalink>
    <type>simple</type>
    <status>publish</status>
    <featured>false</featured>
    <catalog_visibility>visible</catalog_visibility>
    <description>&lt;p&gt;Test Product&lt;/p&gt;
</description>
    <short_description>&lt;p&gt;Test Product&lt;/p&gt;
</short_description>
    <sku>TEST001</sku>
    <price>20</price>
    <regular_price>20</regular_price>
    <sale_price xsi:nil="true" />
    <date_on_sale_from xsi:nil="true" />
    <date_on_sale_from_gmt xsi:nil="true" />
    <date_on_sale_to xsi:nil="true" />
    <date_on_sale_to_gmt xsi:nil="true" />
    <price_html>&lt;span class="woocommerce-Price-amount amount"&gt;&lt;span class="woocommerce-Price-currencySymbol"&gt;&amp;pound;&lt;/span&gt;20.00&lt;/span&gt;</price_html>
    <on_sale>false</on_sale>
    <purchaseable xsi:nil="true" />
    <total_sales>2</total_sales>
    <virtual xsi:nil="true" />
    <downloadable>false</downloadable>
    <downloads />
    <download_limit>-1</download_limit>
    <download_expiry>-1</download_expiry>
    <external_url />
    <button_text />
    <tax_status>taxable</tax_status>
    <tax_class />
    <manage_stock>true</manage_stock>
    <stock_quantity>100</stock_quantity>
    <in_stock>true</in_stock>
    <backorders>no</backorders>
    <backorders_allowed>false</backorders_allowed>
    <backordered>false</backordered>
    <sold_individually>false</sold_individually>
    <weight xsi:nil="true" />
    <dimensions>
      <length>1</length>
      <width>2</width>
      <height>5</height>
    </dimensions>
    <shipping_required>true</shipping_required>
    <shipping_taxable>true</shipping_taxable>
    <shipping_class />
    <shipping_class_id>0</shipping_class_id>
    <reviews_allowed>true</reviews_allowed>
    <average_rating>0.00</average_rating>
    <rating_count>0</rating_count>
    <related_ids>
      <related_id>15</related_id>
      <related_id>10</related_id>
    </related_ids>
    <upsell_ids />
    <cross_sell_ids />
    <parent_id>0</parent_id>
    <purchase_note />
    <categories>
      <category>
        <id>15</id>
        <name>Uncategorised</name>
        <slug>uncategorised</slug>
      </category>
    </categories>
    <tags />
    <images>
      <image>
        <id>28</id>
        <date_created>2018-09-07T13:48:52</date_created>
        <date_created_gmt>2018-09-07T11:48:52</date_created_gmt>
        <date_modified>2018-09-07T13:48:52</date_modified>
        <date_modified_gmt>2018-09-07T11:48:52</date_modified_gmt>
        <src>http://cerulean:8080/wordpress/wp-content/uploads/2017/05/screenshot.png</src>
        <name>screenshot</name>
        <alt />
        <position>0</position>
      </image>
    </images>
    <attributes />
    <default_attributes />
    <variations />
    <grouped_products />
    <menu_order>0</menu_order>
    <meta_data />
  </product>
</products>
```