---
slug: downloading-products-from-magento-v2
redirect_from: "/article/770-downloading-products-from-magento"
title: Downloading Products From Magento V2
---
This task will download products from Magento in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Download Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'All', only products created after this date will be downloaded. This date will update automatically each time the task runs.

### Download Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only products updated after this date will be downloaded. This date will update automatically each time the task runs.

### Download Settings > Export Modified, New or All Records
_Required_  
Choose which records should be downloaded. The available options are:

* __Modified__ - Only records updated after the date shown in the 'Date Modified' setting will be downloaded.
* __New__ - Only records created after the date shown in the 'Date Created' setting will be downloaded.
* __All__ - All records will be downloaded, regardless of when they were created or updated.

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
The name of the file to export the products to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfProduct xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <id>1</id>
    <sku>24-MB01</sku>
    <name>Joust Duffle Bag</name>
    <created_at>2016-02-01T10:57:52</created_at>
    <updated_at>2016-04-07T08:45:54</updated_at>
    <store_id xsi:nil="true" />
    <attribute_set_id>15</attribute_set_id>
    <price>34</price>
    <status>1</status>
    <visibility>4</visibility>
    <type_id>simple</type_id>
    <weight xsi:nil="true" />
    <product_links>
      <product_link>
        <sku>24-MB01</sku>
        <link_type>upsell</link_type>
        <linked_product_sku>24-MB03</linked_product_sku>
        <linked_product_type>simple</linked_product_type>
        <position xsi:nil="true" />
        <extension_attributes />
      </product_link>
      <product_link>
        <sku>24-MB01</sku>
        <link_type>upsell</link_type>
        <linked_product_sku>24-MB05</linked_product_sku>
        <linked_product_type>simple</linked_product_type>
        <position xsi:nil="true" />
        <extension_attributes />
      </product_link>
    </product_links>
    <options />
    <tier_prices />
    <custom_attributes>
      <custom_attribute>
        <attribute_code>description</attribute_code>
        <value><p>The sporty Joust Duffle Bag can't be beat - not in the gym, not on the luggage carousel, not anywhere. Big enough to haul a basketball or soccer ball and some sneakers with plenty of room to spare, it's ideal for athletes with places to go.<p>
<ul>
<li>Dual top handles.</li>
<li>Adjustable shoulder strap.</li>
<li>Full-length zipper.</li>
<li>L 29" x W 13" x H 11".</li>
</ul></value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>color</attribute_code>
        <value>49</value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>options_container</attribute_code>
        <value>container2</value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>required_options</attribute_code>
        <value>0</value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>has_options</attribute_code>
        <value>0</value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>url_key</attribute_code>
        <value>joust-duffle-bag</value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>tax_class_id</attribute_code>
        <value>2</value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>activity</attribute_code>
        <value>11,22,21,19</value>
      </custom_attribute>
    </custom_attributes>
  </Product>
</ArrayOfProduct>
```
