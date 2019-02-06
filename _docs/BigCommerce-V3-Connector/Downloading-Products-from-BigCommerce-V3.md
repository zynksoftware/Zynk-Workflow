---
slug: downloading-products-from-bigcommerce-v3
title: Downloading Products from BigCommerce V3
---
This task will download products from your BigCommerce store to an XML file.

## Settings
### Connection
_Required_  
The BigCommerce connection to use.See the [Connecting to BigCommerce V3](connecting-to-bigcommerce-v3) article if you require more information on how to create/manage connections.

### Export Settings > Date Modified
_Required_  
When the 'Export Type' is set to Modified, only records updated after this date will be downloaded.  The date will update automatically each time the task runs based on the data returned.

### Export Settings > Export Type
_Required_  
Used to choose which records should be included in the download.  The available options are: -

 - **Modified** - Only records created or updated since the task last ran will be downloaded
 - **All** - All records will be downloaded, regardless of whether or not they have been updated since the task last ran

### Output File
_Required_  
The name of the XML file to export the data to (e.g. big_commerce_export_customers.xml).

### Page Size
_Required_  
The number of records returned per page of the request.  Defaults to 50.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below showing the product '[Sample] Tomorrow is today, Red printed scarf'.  For detailed documentation on the fields please see the [BigCommerce Dev Center](https://developer.bigcommerce.com/api-reference/catalog/catalog-api/models/product).

```xml
<?xml version="1.0" encoding="utf-8"?>
<products xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <product>
    <id>32</id>
    <zynk_external_id />
    <date_created>2012-09-21T03:31:01+01:00</date_created>
    <date_modified>2019-01-11T10:10:55+00:00</date_modified>
    <name>[Sample] Tomorrow is today, Red printed scarf</name>
    <type>physical</type>
    <sku>SAMPLE001</sku>
    <description>&lt;p&gt;&lt;strong&gt;How to write product descriptions that sell&lt;/strong&gt;&lt;br /&gt;One of the best things you can do to make your store successful is invest some time in writing great product descriptions. You want to provide detailed yet concise information that will entice potential customers to buy.&lt;br /&gt;&lt;br /&gt;Keep three things in mind:&lt;br /&gt;&lt;br /&gt;&lt;strong&gt;Think like a consumer&lt;/strong&gt;&lt;br /&gt;Think about what you as a consumer would want to know, then include those features in your description. For clothes: materials and fit. For food: ingredients and how it was prepared. Bullets are your friends when listing features &amp;mdash; try to limit each one to 5-8 words.&lt;br /&gt;&lt;br /&gt;&lt;strong&gt;Find differentiators&lt;/strong&gt;&lt;br /&gt;Pepper your features with details that show how the product stands out against similar offerings. For clothes: is it vintage or hard to find? For art: is the artist well known? For home d&amp;eacute;cor: is it a certain style like mid-century modern? Unique product descriptions not only help you stand out, they improve your SEO.&lt;br /&gt;&lt;br /&gt;&lt;strong&gt;Keep it simple&lt;/strong&gt;&lt;br /&gt;Provide enough detail to help consumers make an informed decision, but don&amp;rsquo;t overwhelm with a laundry list of features or flowery language. Densely pack your descriptions with useful information and watch products fly off the shelf.&lt;/p&gt;</description>
    <weight>0.3</weight>
    <width>0</width>
    <depth>0</depth>
    <height>0</height>
    <price>89</price>
    <cost_price>0</cost_price>
    <retail_price>0</retail_price>
    <sale_price>0</sale_price>
    <calculated_price>89</calculated_price>
    <tax_class_id>0</tax_class_id>
    <product_tax_code />
    <categories>
      <category>14</category>
    </categories>
    <brand_id>17</brand_id>
    <inventory_level>45</inventory_level>
    <inventory_warning_level>10</inventory_warning_level>
    <inventory_tracking>variant</inventory_tracking>
    <fixed_cost_shipping_price>10</fixed_cost_shipping_price>
    <is_free_shipping>false</is_free_shipping>
    <is_visible>true</is_visible>
    <is_featured>true</is_featured>
    <related_products>
      <related_product>-1</related_product>
    </related_products>
    <warranty />
    <bin_picking_number />
    <layout_file>product.html</layout_file>
    <upc />
    <search_keywords />
    <availability>available</availability>
    <availability_description />
    <gift_wrapping_options_type>any</gift_wrapping_options_type>
    <gift_wrapping_options />
    <sort_order>0</sort_order>
    <condition>New</condition>
    <is_condition_shown>false</is_condition_shown>
    <order_quantity_minimum>0</order_quantity_minimum>
    <order_quantity_maximum>0</order_quantity_maximum>
    <page_title />
    <meta_keywords />
    <meta_description />
    <view_count>4</view_count>
    <preorder_release_date xsi:nil="true" />
    <preorder_message />
    <is_preorder_only>false</is_preorder_only>
    <is_price_hidden>false</is_price_hidden>
    <price_hidden_label />
    <custom_url>
      <url>/tomorrow-is-today-red-printed-scarf/</url>
      <is_customized>false</is_customized>
    </custom_url>
    <open_graph_type>product</open_graph_type>
    <open_graph_title />
    <open_graph_description />
    <open_graph_use_meta_description>true</open_graph_use_meta_description>
    <open_graph_use_product_name>true</open_graph_use_product_name>
    <open_graph_use_image>true</open_graph_use_image>
    <gtin />
    <mpn />
    <reviews_rating_sum>0</reviews_rating_sum>
    <reviews_count>0</reviews_count>
    <total_sold>0</total_sold>
    <base_variant_id xsi:nil="true" />
  </product>
</products>
```