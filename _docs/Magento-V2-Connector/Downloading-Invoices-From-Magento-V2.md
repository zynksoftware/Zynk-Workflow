---
slug: downloading-invoices-from-magento-v2
redirect_from: "/article/767-downloading-invoices-from-magento"
title: Downloading Invoices From Magento V2
---
This task will download invoices from Magento in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Download Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'All', only invoices created after this date will be downloaded. This date will update automatically each time the task runs.

### Download Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only invoices updated after this date will be downloaded. This date will update automatically each time the task runs.

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
The name of the file to export the invoices to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <base_currency_code>GBP</base_currency_code>
    <base_discount_amount>0</base_discount_amount>
    <base_grand_total>34</base_grand_total>
    <base_discount_tax_compensation_amount>0</base_discount_tax_compensation_amount>
    <base_shipping_amount>5</base_shipping_amount>
    <base_shipping_discount_amount xsi:nil="true" />
    <base_shipping_discount_tax_compensation_amnt xsi:nil="true" />
    <base_shipping_incl_tax>5</base_shipping_incl_tax>
    <base_shipping_tax_amount>0</base_shipping_tax_amount>
    <base_subtotal>29</base_subtotal>
    <base_subtotal_incl_tax>0</base_subtotal_incl_tax>
    <base_tax_amount>0</base_tax_amount>
    <base_total_refunded xsi:nil="true" />
    <base_to_global_rate>1</base_to_global_rate>
    <base_to_order_rate>1</base_to_order_rate>
    <billing_address_id>2</billing_address_id>
    <can_void_flag>0</can_void_flag>
    <created_at>2016-01-06T16:23:00</created_at>
    <discount_amount>0</discount_amount>
    <email_sent xsi:nil="true" />
    <entity_id>1</entity_id>
    <global_currency_code>GBP</global_currency_code>
    <grand_total>34</grand_total>
    <discount_tax_compensation_amount>0</discount_tax_compensation_amount>
    <increment_id>000000001</increment_id>
    <is_used_for_refund xsi:nil="true" />
    <order_currency_code>GBP</order_currency_code>
    <order_id>1</order_id>
    <shipping_address_id>1</shipping_address_id>
    <shipping_amount>5</shipping_amount>
    <shipping_discount_tax_compensation_amount>0</shipping_discount_tax_compensation_amount>
    <shipping_incl_tax>5</shipping_incl_tax>
    <shipping_tax_amount>0</shipping_tax_amount>
    <state>2</state>
    <store_currency_code>GBP</store_currency_code>
    <store_id>1</store_id>
    <store_to_base_rate xsi:nil="true" />
    <store_to_order_rate xsi:nil="true" />
    <subtotal>29</subtotal>
    <subtotal_incl_tax>0</subtotal_incl_tax>
    <tax_amount>0</tax_amount>
    <total_qty>1</total_qty>
    <updated_at>2016-01-06T16:23:00</updated_at>
    <items>
      <item>
        <base_cost xsi:nil="true" />
        <base_discount_amount xsi:nil="true" />
        <base_discount_tax_compensation_amount xsi:nil="true" />
        <base_price>0</base_price>
        <base_price_incl_tax xsi:nil="true" />
        <base_row_total>0</base_row_total>
        <base_row_total_incl_tax xsi:nil="true" />
        <base_tax_amount xsi:nil="true" />
        <discount_amount xsi:nil="true" />
        <entity_id>1</entity_id>
        <discount_tax_compensation_amount xsi:nil="true" />
        <name>Iris Workout Top-XS-Red</name>
        <order_item_id>1</order_item_id>
        <parent_id>1</parent_id>
        <price>0</price>
        <price_incl_tax xsi:nil="true" />
        <product_id>1420</product_id>
        <qty>1</qty>
        <row_total>0</row_total>
        <row_total_incl_tax xsi:nil="true" />
        <sku>WS03-XS-Red</sku>
        <tax_amount xsi:nil="true" />
      </item>
    </items>
    <comments />
  </Invoice>
</ArrayOfInvoice>
```
