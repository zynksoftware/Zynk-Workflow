---
slug: downloading-products-from-woocommerce
redirect_from: "/article/338-downloading-products-from-woocommerce"
title: Downloading Products from WooCommerce
---
This task will download products from your WooCommerce store to an XML file.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce) article if you require more information on how to create/manage connections.

### Download Meta Data
_Required_  
Set to true to download additional meta data for the products. Defaults to false.

### Download Setting > Date Created
_Required_  
The date to download products from when the task is set to download new orders. Updates automatically each time a product is downloaded.

### Download Setting > Date Modified
_Required_  
The date to download products from when the task is set to download modified orders. Updates automatically each time a product is downloaded.

### Download Setting > Export Modified, New or All Records
_Required_  
Choose which products should be downloaded from WooCommerce. The available options are:

* __Modified__ - Downloads updated products since the date shown in the Date Modified setting.
* __New__ - Downloads new products since the date shown in the Date Created setting.
* __All__ - Downloads all products.

### Page Size
_Required_  
The number of products to download per page. Increasing this value will speed up the download, but will consume more memory. Defaults to 10.

### Output File
_Required_  
The name of the XML file to export the products to. Defaults to 'woo_commerce_products.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductList>
  <products>
    <product>
      <id>8</id>
      <created_at>2015-03-11T17:06:18</created_at>
      <updated_at>2015-03-26T10:53:09</updated_at>
      <title>Test Product</title>
      <type>simple</type>
      <status>publish</status>
      <downloadable>false</downloadable>
      <virtual>false</virtual>
      <permalink>https://localhost:8080/wordpress-4.1.1/product/test/</permalink>
      <sku>ABC123</sku>
      <price>8.00</price>
      <regular_price>10.00</regular_price>
      <sales_price xsi:nil="true" />
      <sales_price_dates_from xsi:nil="true" />
      <sales_price_dates_to xsi:nil="true" />
      <price_html><del><span class="amount">&pound;10.00</span></del> <ins><span class="amount">&pound;8.00</span></ins></price_html>
      <taxable>false</taxable>
      <tax_status>taxable</tax_status>
      <tax_class />
      <managing_stock>true</managing_stock>
      <stock_quantity>88</stock_quantity>
      <in_stock>true</in_stock>
      <backorders_allowed>false</backorders_allowed>
      <backordered>false</backordered>
      <sold_individually>false</sold_individually>
      <purchaseable>true</purchaseable>
      <featured>false</featured>
      <visible>true</visible>
      <catalog_visibility>visible</catalog_visibility>
      <on_sale>true</on_sale>
      <weight xsi:nil="true" />
      <dimensions>
        <length xsi:nil="true" />
        <width xsi:nil="true" />
        <height xsi:nil="true" />
        <unit>cm</unit>
      </dimensions>
      <shipping_required>true</shipping_required>
      <shipping_taxable>true</shipping_taxable>
      <shipping_class />
      <shipping_class_id xsi:nil="true" />
      <description><p>Just a test product</p>
</description>
      <short_description />
      <reviews_allowed>true</reviews_allowed>
      <average_rating>0.00</average_rating>
      <rating_count>0</rating_count>
      <parent_id>0</parent_id>
      <categories>
        <category>Stationary</category>
      </categories>
      <images>
        <image>
          <id>0</id>
          <created_at>2015-03-26T13:02:09</created_at>
          <updated_at>2015-03-26T13:02:09</updated_at>
          <src>https://localhost:8080/wordpress-4.1.1/wp-content/plugins/woocommerce/assets/images/placeholder.png</src>
          <title>Placeholder</title>
          <alt>Placeholder</alt>
          <position>0</position>
        </image>
      </images>
      <featured_src>False</featured_src>
      <download_limit>0</download_limit>
      <download_expiry>0</download_expiry>
      <download_type />
      <purchase_note />
      <total_sales>1</total_sales>
      <product_meta>
        <total_sales>1</total_sales>
      </product_meta>
    </product>
  </products>
</ProductList>
```