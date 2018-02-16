---
slug: downloading-product-attributes-from-magento
redirect_from: "/article/264-downloading-product-attributes-from-magento"
title: Downloading Product Attributes from Magento
---
This task will download a list of product attributes from Magento in XML format. The list of options is also provided when the attribute type is a select list.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Attribute Set ID
_Optional_  
Enter the ID of a particular attribute set to download, or leave blank to download all attribute sets.

### Output File
_Required_  
The name of the file to export the products to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0"?>
<ArrayOfProductAttribute>
  <ProductAttribute>
    <Fields>
      <Field Name="frontend_input" Value="text" />
      <Field Name="default_value" Value="" />
      <Field Name="is_unique" Value="0" />
      <Field Name="apply_to" Value="" />
      <Field Name="is_configurable" Value="1" />
      <Field Name="is_searchable" Value="1" />
      <Field Name="is_visible_in_advanced_search" Value="1" />
      <Field Name="is_comparable" Value="0" />
      <Field Name="is_used_for_promo_rules" Value="0" />
      <Field Name="is_visible_on_front" Value="0" />
      <Field Name="used_in_product_listing" Value="1" />
      <Field Name="frontend_label" Value="" />
      <Field Name="additional_fields" Value="" />
    </Fields>
    <attribute_id>71</attribute_id>
    <attribute_code>name</attribute_code>
    <is_required>1</is_required>
    <scope>store</scope>
  </ProductAttribute>
  <ProductAttribute>
    <Fields>
      <Field Name="frontend_input" Value="text" />
      <Field Name="default_value" Value="" />
      <Field Name="is_unique" Value="1" />
      <Field Name="apply_to" Value="" />
      <Field Name="is_configurable" Value="1" />
      <Field Name="is_searchable" Value="1" />
      <Field Name="is_visible_in_advanced_search" Value="1" />
      <Field Name="is_comparable" Value="1" />
      <Field Name="is_used_for_promo_rules" Value="0" />
      <Field Name="is_visible_on_front" Value="0" />
      <Field Name="used_in_product_listing" Value="0" />
      <Field Name="frontend_label" Value="" />
      <Field Name="additional_fields" Value="" />
    </Fields>
    <attribute_id>74</attribute_id>
    <attribute_code>sku</attribute_code>
    <is_required>1</is_required>
    <scope>global</scope>
  </ProductAttribute>
  <ProductAttribute>
    <Fields>
      <Field Name="frontend_input" Value="select" />
      <Field Name="default_value" Value="" />
      <Field Name="is_unique" Value="0" />
      <Field Name="apply_to" Value="" />
      <Field Name="is_configurable" Value="1" />
      <Field Name="is_searchable" Value="1" />
      <Field Name="is_visible_in_advanced_search" Value="0" />
      <Field Name="is_comparable" Value="0" />
      <Field Name="is_used_for_promo_rules" Value="0" />
      <Field Name="is_visible_on_front" Value="0" />
      <Field Name="used_in_product_listing" Value="1" />
      <Field Name="frontend_label" Value="" />
      <Field Name="additional_fields" Value="" />
    </Fields>
    <attribute_id>96</attribute_id>
    <attribute_code>status</attribute_code>
    <is_required>1</is_required>
    <scope>website</scope>
    <options>
      <ProductAttributeOption>
        <Fields />
        <value>1</value>
        <label>Enabled</label>
      </ProductAttributeOption>
      <ProductAttributeOption>
        <Fields />
        <value>2</value>
        <label>Disabled</label>
      </ProductAttributeOption>
    </options>
  </ProductAttribute>
</ArrayOfProductAttribute>
``` 