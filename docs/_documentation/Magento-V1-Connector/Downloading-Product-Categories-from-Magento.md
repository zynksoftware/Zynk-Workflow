---
slug: downloading-product-categories-from-magento
redirect_from: "/article/265-downloading-product-categories-from-magento"
title: Downloading Product Categories from Magento
---
This task will download a list of all product categories from Magento in XML format.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the product categories to.

### Download Detailed
_Required_  
Set to true to download detailed category data, or false to just download the category tree containing the category names and IDs.

### Parent Category ID
_Optional_  
Enter the ID of the category to download a list of sub categories from, or leave blank to download all sub categories from the root level.


### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file, when Download Detailed is set to true:
```xml
<?xml version="1.0"?>
<ArrayOfCategory>
  <Category>
    <Fields>
      <Field Name="thumbnail" Value="" />
      <Field Name="children_count" Value="3" />
      <Field Name="filter_price_range" Value="" />
      <Field Name="custom_use_parent_settings" Value="" />
      <Field Name="custom_apply_to_products" Value="" />
    </Fields>
    <all_children>1,2,3,4</all_children>
    <created_at>2014-01-17 12:59:14</created_at>
    <category_id>1</category_id>
    <parent_id>0</parent_id>
    <path>1</path>
    <children>2</children>
    <url_key>root-catalog</url_key>
    <name>Root Catalog</name>
    <position>0</position>
    <level>0</level>
    <updated_at>2014-01-17 12:59:14</updated_at>
    <include_in_menu>1</include_in_menu>
  </Category>
  <Category>
    <Fields>
      <Field Name="thumbnail" Value="" />
      <Field Name="children_count" Value="2" />
      <Field Name="filter_price_range" Value="" />
      <Field Name="custom_use_parent_settings" Value="" />
      <Field Name="custom_apply_to_products" Value="0" />
    </Fields>
    <display_mode>PRODUCTS</display_mode>
    <all_children>2,3,4</all_children>
    <created_at>2014-01-17 12:59:15</created_at>
    <category_id>2</category_id>
    <parent_id>1</parent_id>
    <parent_name>Root Catalog</parent_name>
    <is_anchor>0</is_anchor>
    <path>1/2</path>
    <children>3,4</children>
    <is_active>1</is_active>
    <url_key>office-supplies</url_key>
    <name>Office Supplies</name>
    <position>1</position>
    <level>1</level>
    <updated_at>2014-07-24 11:56:24</updated_at>
    <include_in_menu>1</include_in_menu>
  </Category>
  <Category>
    <Fields>
      <Field Name="thumbnail" Value="" />
      <Field Name="children_count" Value="0" />
      <Field Name="filter_price_range" Value="" />
      <Field Name="custom_use_parent_settings" Value="0" />
      <Field Name="custom_apply_to_products" Value="0" />
    </Fields>
    <display_mode>PRODUCTS</display_mode>
    <all_children>3</all_children>
    <created_at>2014-07-24 11:46:22</created_at>
    <category_id>3</category_id>
    <parent_id>2</parent_id>
    <parent_name>Office Supplies</parent_name>
    <is_anchor>0</is_anchor>
    <url_path>stationary.html</url_path>
    <path>1/2/3</path>
    <children />
    <meta_title>Stationary</meta_title>
    <is_active>1</is_active>
    <description>This is our collection of stationary supplies</description>
    <url_key>stationary</url_key>
    <name>Stationary</name>
    <position>1</position>
    <level>2</level>
    <updated_at>2014-07-24 11:46:22</updated_at>
    <include_in_menu>1</include_in_menu>
  </Category>
  <Category>
    <Fields>
      <Field Name="thumbnail" Value="" />
      <Field Name="children_count" Value="0" />
      <Field Name="filter_price_range" Value="" />
      <Field Name="custom_use_parent_settings" Value="0" />
      <Field Name="custom_apply_to_products" Value="0" />
    </Fields>
    <display_mode>PRODUCTS</display_mode>
    <all_children>4</all_children>
    <created_at>2014-07-24 11:48:16</created_at>
    <category_id>4</category_id>
    <parent_id>2</parent_id>
    <parent_name>Office Supplies</parent_name>
    <is_anchor>0</is_anchor>
    <url_path>office-equipment.html</url_path>
    <path>1/2/4</path>
    <children />
    <meta_title>Office Equipment</meta_title>
    <is_active>1</is_active>
    <description>We stock a wide range of office equipment.</description>
    <url_key>office-equipment</url_key>
    <name>Office Equipment</name>
    <position>2</position>
    <level>2</level>
    <updated_at>2014-07-24 11:48:16</updated_at>
    <include_in_menu>1</include_in_menu>
  </Category>
</ArrayOfCategory>
```

Sample output file, when Download Detailed is set to false:
```xml
<?xml version="1.0"?>
<ArrayOfCategory>
  <Category>
    <Fields />
    <category_id>1</category_id>
    <parent_id>0</parent_id>
    <name>Root Catalog</name>
    <position>0</position>
    <level>0</level>
  </Category>
  <Category>
    <Fields />
    <category_id>2</category_id>
    <parent_id>1</parent_id>
    <name>Office Supplies</name>
    <position>1</position>
    <level>1</level>
  </Category>
  <Category>
    <Fields />
    <category_id>3</category_id>
    <parent_id>2</parent_id>
    <name>Stationary</name>
    <position>1</position>
    <level>2</level>
  </Category>
  <Category>
    <Fields />
    <category_id>4</category_id>
    <parent_id>2</parent_id>
    <name>Office Equipment</name>
    <position>2</position>
    <level>2</level>
  </Category>
</ArrayOfCategory>
```