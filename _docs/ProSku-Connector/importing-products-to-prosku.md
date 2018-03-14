---
slug: importing-products-to-prosku
redirect_from: "/article/importing-products-to-prosku"
title: Importing Products to ProSKU
---
This task will upload products that are supplied in an XML format.

## Fields
The below fields in bold are required when creating a product or changing a product. The other fields are optional when creating and updating. 

* __product_code__
* description
* code2
* code3
* __barcode__
* keywords
* cost_price
* sales_price
* active
* __storage_uom__
* __secondary_uom__
* __height__ if Depth and Width are also recorded
* __width__  if Height and Depth are also recorded
* __depth__  if Height and Width are also recorded
* weight
* items_per_unit
* storage_volume
* required_volume
* use_size_to_set_volume
* serial_number_in
* __serial_number_out__  if product records serial number in
* required_batch_no
* __record_rotation_date__ if product requires rotation by rotation date
* supplier_details
* rotation_display_format
* auto_putaway
* __auto_putaway_option__ if auto_putaway
* store_by_volume
* store_together_different_rotation
* top_up
* force_top_up
* mix_with_other_products
* product_groups
* __min_stock_level__  if auto_putaway
* __rotation_by__  if product requires rotation
* strict_rotation
* picking_location
* min_replen_quantity
* max_replen_quantity
* enforce_replen_rotation
* enforce_pickface_picking
* custom_fields

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
Sample input file, for full documentation and samples see [ProSKU Products XML](prosku-products-xml):  
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<products>
	<product>
	  <product_lines>
		<product_line>
		  <product_code>Phantom</product_code>
		  <description>Phantom Description</description>
		  <code2>code2</code2>
		  <code3 />
		  <barcode>Phantom1a25</barcode>
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
		  <product_groups>PG2</product_groups>
		  <min_stock_level>0</min_stock_level>
		  <rotate_by>FIFO</rotate_by>
		  <strict_rotation>false</strict_rotation>
		  <picking_location />
		  <min_replen_quantity>0</min_replen_quantity>
		  <max_replen_quantity>0</max_replen_quantity>
		  <enforce_replen_rotation>false</enforce_replen_rotation>
		  <enforce_pickface_picking>false</enforce_pickface_picking>
		</product_line>
	  </product_lines>
	</product>
	<product>
	  <product_lines>
		<product_line>
		  <product_code>Phantom1</product_code>
		  <description>Phantom1 Description</description>
		  <code2>code2</code2>
		  <code3 />
		  <barcode>Phantom11a25</barcode>
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
		  <rotation_display_format>MM/YY</rotation_display_format>
		  <auto_putaway>false</auto_putaway>
		  <auto_putaway_option>
			<type>Zone</type>
			<code>01</code>
		  </auto_putaway_option>
          <supplier_details>SUP01</supplier_details>
          <supplier_details>SUP02</supplier_details>
		  <store_by_volume>false</store_by_volume>
		  <store_together_same_rotation>false</store_together_same_rotation>
		  <store_together_different_rotation>false</store_together_different_rotation>
		  <top_up>false</top_up>
		  <force_top_up>false</force_top_up>
		  <mix_with_other_products />
		  <product_groups>PG2</product_groups>
		  <min_stock_level>0</min_stock_level>
		  <rotate_by>FIFO</rotate_by>
		  <strict_rotation>false</strict_rotation>
		  <picking_location />
		  <min_replen_quantity>0</min_replen_quantity>
		  <max_replen_quantity>0</max_replen_quantity>
		  <enforce_replen_rotation>false</enforce_replen_rotation>
		  <enforce_pickface_picking>false</enforce_pickface_picking>
		</product_line>
	  </product_lines>
	</product>
	<product>
	  <product_lines>
		<product_line>
		  <product_code>Phantom2</product_code>
		  <description>Phantom2 Description</description>
		  <code2>code2</code2>
		  <code3 />
		  <barcode>Phantom21a25</barcode>
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
          <supplier_details>SUP01</supplier_details>
          <supplier_details>SUP02</supplier_details>
		  <items_per_unit>1</items_per_unit>
		  <storage_volume>0.0</storage_volume>
		  <require_volume>false</require_volume>
		  <use_size_to_set_volume>false</use_size_to_set_volume>
		  <serial_number_in>false</serial_number_in>
		  <serial_number_out>false</serial_number_out>
		  <require_batch_no>false</require_batch_no>
		  <record_rotation_date>false</record_rotation_date>
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
		  <product_groups>PG2</product_groups>
		  <min_stock_level>0</min_stock_level>
		  <rotate_by>FIFO</rotate_by>
		  <strict_rotation>false</strict_rotation>
		  <picking_location />
		  <min_replen_quantity>0</min_replen_quantity>
		  <max_replen_quantity>0</max_replen_quantity>
		  <enforce_replen_rotation>false</enforce_replen_rotation>
		  <enforce_pickface_picking>false</enforce_pickface_picking>
		</product_line>
	  </product_lines>
	</product>
</products>
```
