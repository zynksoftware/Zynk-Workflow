---
slug: uploading-products-to-bigcommerce
redirect_from: "/article/172-uploading-products-to-bigcommerce"
title: Uploading Products to BigCommerce
---
This task will update existing or insert new products on your BigCommerce store.

## Settings
### Connection
_Required_  
The BigCommerce connection to use. See the [Connecting to BigCommerce](connecting-to-bigcommerce) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed uploads to.

### Input File
_Required_  
The XML file containing the product updates. These should be stored in the same format as products downloaded using the 'Download Products' task.

If a `<product>` node contains an `<id>` node, it will be treated as an existing product and the task will attempt to update it in BigCommerce. When updating existing products, please note that the `<rating_total>`, `<rating_count>`, `<number_sold>`, `<date_created>`, `<date_modified>`, `<date_last_imported>` and `<custom_url>` nodes are read-only and will result in an error if you try to update them.

If no `<id>` node is provided for the product, it will be treat as a new product and the task will attempt to create it in BigCommerce. When creating new products, a `<name>`, `<price>`, `<categories>`, `<type>`, `<availability>`, and `<weight>` node must be provided, and the `<rating_total>`, `<rating_count>`, `<number_sold>`, `<date_created>`, `<date_modified>`, `<date_last_imported>` and `<custom_url>` cannot be provided as they are read-only.

### Success File
_Required_  
The XML file to output successful updates to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<products>
  <!-- New product -->
  <product>
    <name>FX010 Plain Paper Fax</name>
    <type>physical</type>
    <sku>FAX001</sku>
    <description>FX010 Plain Paper Fax</description>
    <price>15.0000</price>
    <cost_price>0.0000</cost_price>
    <retail_price>0.0000</retail_price>
    <sale_price>0.0000</sale_price>
    <is_visible>false</is_visible>
    <is_featured>false</is_featured>
    <weight>0.0000</weight>
    <categories>
      <value>18</value>
    </categories>
    <tax_class_id>0</tax_class_id>
    <availability>available</availability>
  </product>
  <!-- Update for an existing product -->
  <product>
    <id>101</id>
    <name>FX010 Plain Paper Fax 2</name>
    <type>physical</type>
    <sku>FAX002</sku>
    <description>FX010 Plain Paper Fax 2</description>
    <price>16.0000</price>
    <cost_price>0.0000</cost_price>
    <retail_price>0.0000</retail_price>
    <sale_price>0.0000</sale_price>
    <is_visible>false</is_visible>
    <is_featured>false</is_featured>
    <weight>0.0000</weight>
    <categories>
      <value>18</value>
    </categories>
    <tax_class_id>0</tax_class_id>
    <availability>available</availability>
  </product>
</products>
```