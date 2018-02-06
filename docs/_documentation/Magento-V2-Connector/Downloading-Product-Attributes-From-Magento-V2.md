---
slug: downloading-product-attributes-from-magento-v2
redirect_from: "/article/769-downloading-product-attributes-from-magento"
title: Downloading Product Attributes From Magento V2
---
This task will download product attributes from Magento in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Filter Groups
_Optional_  
The filtering to apply to the records. Only records which match the criteria specified will be downloaded.

Filters are arranged into groups. The individual filters within a group will be combined using the OR operator. Groups of filters are combined using the AND operator.

### Filter Groups > Filter > Condition
_Optional_  
The following types of filter are available:

* __Equal__ - Returns records where the field matches the specified value.
* __NotEqual__ - Returns records where the field does not match the specified value.
* __Like__ - Returns records where the field contains the specified value.
* __In__ - Returns records where the field matches one of the specified values.
* __NotIn__ - Returns records where the field does not match one of the specified values.
* __Null__ - Returns records where the field does not have a value.
* __NotNull__ - Returns records where the field has a value.
* __GreaterThan__ - Returns records where the field is greater than the specified value.
* __LessThan__ - Returns records where the field is less than the specified value.
* __GreaterThanOrEqual__ - Returns records where the field is greater than or equal to the specified value.
* __LessThanOrEqual__ - Returns records where the field is less than or equal to the specified value.

### Filter Groups > Filter > Field
_Optional_  
The name of the field the filter is to be based upon. The name should match the API field name, as seen in the output file.

### Filter Groups > Filter > Value
_Optional_  
The value the filter is to be based upon. This is not required when using the 'Null' or 'NotNull' condition type.

### Page Size
_Required_  
The number of records to include in each page of results. Defaults to 50. Increasing this value will increase the speed of the download, but will consume more memory.

### Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'default'.

### Output File
_Required_  
The name of the file to export the product attributes to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfProductAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ProductAttribute>
    <is_wysiwyg_enabled>false</is_wysiwyg_enabled>
    <is_html_allowed_on_front>false</is_html_allowed_on_front>
    <used_for_sort_by>true</used_for_sort_by>
    <is_filterable>false</is_filterable>
    <is_filterable_in_search>false</is_filterable_in_search>
    <is_used_in_grid>false</is_used_in_grid>
    <is_visible_in_grid>false</is_visible_in_grid>
    <is_filterable_in_grid>false</is_filterable_in_grid>
    <position>0</position>
    <apply_to />
    <is_searchable>1</is_searchable>
    <is_visible_in_advanced_search>1</is_visible_in_advanced_search>
    <is_comparable>0</is_comparable>
    <is_used_for_promo_rules>0</is_used_for_promo_rules>
    <is_visible_on_front>0</is_visible_on_front>
    <used_in_product_listing>1</used_in_product_listing>
    <is_visible>true</is_visible>
    <scope>store</scope>
    <attribute_id>70</attribute_id>
    <attribute_code>name</attribute_code>
    <frontend_input>text</frontend_input>
    <entity_type_id>4</entity_type_id>
    <is_required>true</is_required>
    <options />
    <is_user_defined>false</is_user_defined>
    <default_frontend_label>Name</default_frontend_label>
    <backend_type>varchar</backend_type>
    <is_unique>0</is_unique>
    <frontend_class>validate-length maximum-length-255</frontend_class>
    <validation_rules />
  </ProductAttribute>
  <ProductAttribute>
    <is_wysiwyg_enabled>false</is_wysiwyg_enabled>
    <is_html_allowed_on_front>false</is_html_allowed_on_front>
    <used_for_sort_by>false</used_for_sort_by>
    <is_filterable>false</is_filterable>
    <is_filterable_in_search>false</is_filterable_in_search>
    <is_used_in_grid>true</is_used_in_grid>
    <is_visible_in_grid>false</is_visible_in_grid>
    <is_filterable_in_grid>true</is_filterable_in_grid>
    <position>0</position>
    <apply_to>
      <string>simple</string>
      <string>virtual</string>
      <string>bundle</string>
      <string>downloadable</string>
      <string>configurable</string>
    </apply_to>
    <is_searchable>1</is_searchable>
    <is_visible_in_advanced_search>0</is_visible_in_advanced_search>
    <is_comparable>0</is_comparable>
    <is_used_for_promo_rules>0</is_used_for_promo_rules>
    <is_visible_on_front>0</is_visible_on_front>
    <used_in_product_listing>1</used_in_product_listing>
    <is_visible>true</is_visible>
    <scope>website</scope>
    <attribute_id>129</attribute_id>
    <attribute_code>tax_class_id</attribute_code>
    <frontend_input>select</frontend_input>
    <entity_type_id>4</entity_type_id>
    <is_required>false</is_required>
    <options>
      <option>
        <label>None</label>
        <value>0</value>
        <sort_order xsi:nil="true" />
        <is_default xsi:nil="true" />
      </option>
      <option>
        <label>Taxable Goods</label>
        <value>2</value>
        <sort_order xsi:nil="true" />
        <is_default xsi:nil="true" />
      </option>
    </options>
    <is_user_defined>false</is_user_defined>
    <default_frontend_label>Tax Class</default_frontend_label>
    <backend_type>int</backend_type>
    <source_model>Magento\Tax\Model\TaxClass\Source\Product</source_model>
    <default_value>2</default_value>
    <is_unique>0</is_unique>
    <validation_rules />
  </ProductAttribute>
</ArrayOfProductAttribute>
```
