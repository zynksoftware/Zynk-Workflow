---
slug: prosku-products-xml
title: ProSKU Product XML
---
Import Products allows you to create new and update existing product records in ProSKU. 

Any ProSKU fields not documented below are not supported with our uploads. 

Sample upload file for creating a product record in ProSKU:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
  <products>
    <product>
      <product_lines>
        <product_line>
          <product_code>Gopro</product_code>
          <description>HD Camera</description>
          <code2>code2</code2>
          <code3 />
          <barcode>GoPro123</barcode>
          <keywords />
          <cost_price>0.0</cost_price>
          <sales_price>0.0</sales_price>
          <active>true</active>
          <storage_uom>Case</storage_uom>
          <secondary_uom />
          <height>0</height>
          <width>0</width>
          <depth>0</depth>
          <weight>0.0</weight>
          <items_per_unit>1</items_per_unit>
          <storage_volume>0.0</storage_volume>
          <require_volume>false</require_volume>
          <use_size_to_set_volume>false</use_size_to_set_volume>
          <serial_number_in>false</serial_number_in>
          <serial_number_out>false</serial_number_out>
          <require_batch_no>false</require_batch_no>
          <record_rotation_date>false</record_rotation_date>
          <supplier_details>SUP01</supplier_details>
          <supplier_details>SUP02</supplier_details>
          <rotation_display_format>MM/YY</rotation_display_format>
          <auto_putaway>false</auto_putaway>
          <auto_putaway_option>
            <type>Zone</type>
            <code>01</code>
          </auto_putaway_option>
          <store_by_volume>false</store_by_volume>
          <store_together_same_rotation>false</store_together_same_rotation>
          <store_together_different_rotation>false</store_together_different_rotation>
          <top_up>false</top_up>
          <force_top_up>false</force_top_up>
          <mix_with_other_products />
          <product_groups>PG1</product_groups>
          <product_groups>PG2</product_groups>
          <min_stock_level>0</min_stock_level>
          <rotate_by>FIFO</rotate_by>
          <strict_rotation>false</strict_rotation>
          <picking_location />
          <min_replen_quantity>0</min_replen_quantity>
          <max_replen_quantity>0</max_replen_quantity>
          <enforce_replen_rotation>false</enforce_replen_rotation>
          <enforce_pickface_picking>false</enforce_pickface_picking>
          <custom_fields>
            <field1_name>field_value</field1_name>
          </custom_fields>
          <custom_fields>
            <field2_name>field2_value</field2_name>
          </custom_fields>
        </product_line>
      </product_lines>
    </product>
  </products>
```

## Product Details
The below information is in relation to the customer details you are able to set using Zynk.

| XML Field | Example | Field Type | Input |
| --- | --- | --- | --- |
| Product_code | Phantom | string | Required |
| Description | This item doesn't exist | string  | Optional |
| Code2 | code2 | string | Optional |
| Code3 |code3 | string | Required |
| Barcode | Phantom1a23 | string   | Required if product requires barcode |
| Keywords | 20  | double   | Optional  |
| Cost_price | 4.99  | double   | Optional  |
| Sale_price | 12.99  | double  | Optional |
| Active | true  | boolean   | Optional  |
| Storage_uom | Case | string   | Required |
| Secondary_uom | Each | string   | Required if product comes on different measuring units |
| Height | 10 | integer   | Required if Depth and Width are also recorded |
| Width | 40 | integer   | Required if Height and Depth are also recorded |
| Depth | 25 | integer   | Required if Height and Width are also recorded |
| Weight | 0.0 | integer   | Optional  |
| Items_per_unit | 2 | integer   | Optional  |
| Storage_volume | true  | boolean   | Optional  |
| Require_volume | true  | boolean   | Optional  |
| Use_size_to_set_volume | true  | boolean   | Optional  |
| Serial_number_in | true  | boolean   | Optional  |
| Serial_number_out | true  | boolean   | Required if product records serial numbers in |
| Required_batch_no | true  | boolean   | Optional  |
| Record_rotation_date | true  | boolean   | Required if product requires rotation by rotation date |
| Rotation_display_format | MM/YY | string   | Optional  |
| Auto_putaway | true  | boolean   | Optional  |
| Auto_putaway_option | Zone, 01 | hash   | Required if Auto_putaway |
| Supplier_details | true  | array   | Optional  |
| Store_by_volume | true  | boolean   | Optional  |
| Store_together_same_rotation | true  | boolean   | Optional  |
| Store_together_different_rotation | true  | boolean   | Optional  |
| top_up | true  | boolean   | Optional  |
| force_top_up | true  | boolean   | Optional  |
| mix_with_other_products | true  | boolean   | Optional  |
| product_groups | PG1 | array   | Optional  |
| min_stock_level | true  | integer   | Required if auto_putaway |
| rotate_by | FIFO | string   | Required if product requires rotation |
| strict_rotation | true  | boolean   | Optional  |
| picking_location | true  | string   | Optional  |
| min_replen_quantity | 1 | integer   | Optional  |
| max_replen_quantity | 10 | integer   | Optional  |
| enforce_replen_rotation | true  | boolean   | Optional  |
| enforce_pickface_picking | true  | boolean   | Optional  |
| custom_fields | true  | array of hashes   | Optional  |


