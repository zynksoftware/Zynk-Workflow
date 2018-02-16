---
slug: downloading-orders-from-magento-v2
redirect_from: "/article/768-downloading-orders-from-magento"
title: Downloading Orders From Magento V2
---
This task will download orders from Magento in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Download Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'All', only orders created after this date will be downloaded. This date will update automatically each time the task runs.

### Download Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only orders updated after this date will be downloaded. This date will update automatically each time the task runs.

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
The name of the file to export the orders to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfSalesOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrder>
    <adjustment_negative xsi:nil="true" />
    <adjustment_positive xsi:nil="true" />
    <base_adjustment_negative xsi:nil="true" />
    <base_adjustment_positive xsi:nil="true" />
    <base_currency_code>GBP</base_currency_code>
    <base_discount_amount>0</base_discount_amount>
    <base_discount_canceled xsi:nil="true" />
    <base_discount_invoiced>0</base_discount_invoiced>
    <base_discount_refunded xsi:nil="true" />
    <base_grand_total>34</base_grand_total>
    <base_discount_tax_compensation_amount>0</base_discount_tax_compensation_amount>
    <base_discount_tax_compensation_invoiced xsi:nil="true" />
    <base_discount_tax_compensation_refunded xsi:nil="true" />
    <base_shipping_amount>5</base_shipping_amount>
    <base_shipping_canceled xsi:nil="true" />
    <base_shipping_discount_amount>0</base_shipping_discount_amount>
    <base_shipping_discount_tax_compensation_amnt xsi:nil="true" />
    <base_shipping_incl_tax>5</base_shipping_incl_tax>
    <base_shipping_invoiced>5</base_shipping_invoiced>
    <base_shipping_refunded xsi:nil="true" />
    <base_shipping_tax_amount>0</base_shipping_tax_amount>
    <base_shipping_tax_refunded xsi:nil="true" />
    <base_subtotal>29</base_subtotal>
    <base_subtotal_canceled xsi:nil="true" />
    <base_subtotal_incl_tax>29</base_subtotal_incl_tax>
    <base_subtotal_invoiced>29</base_subtotal_invoiced>
    <base_subtotal_refunded xsi:nil="true" />
    <base_tax_amount>0</base_tax_amount>
    <base_tax_canceled xsi:nil="true" />
    <base_tax_invoiced>0</base_tax_invoiced>
    <base_tax_refunded xsi:nil="true" />
    <base_total_canceled xsi:nil="true" />
    <base_total_due>0</base_total_due>
    <base_total_invoiced>34</base_total_invoiced>
    <base_total_invoiced_cost>0</base_total_invoiced_cost>
    <base_total_offline_refunded xsi:nil="true" />
    <base_total_online_refunded xsi:nil="true" />
    <base_total_paid>34</base_total_paid>
    <base_total_qty_ordered xsi:nil="true" />
    <base_total_refunded xsi:nil="true" />
    <base_to_global_rate>1</base_to_global_rate>
    <base_to_order_rate>1</base_to_order_rate>
    <billing_address>
      <address_type>billing</address_type>
      <city>Calder</city>
      <country_id>US</country_id>
      <customer_address_id>1</customer_address_id>
      <customer_id xsi:nil="true" />
      <email>roni_cost@example.com</email>
      <entity_id>2</entity_id>
      <firstname>Veronica</firstname>
      <lastname>Costello</lastname>
      <parent_id>1</parent_id>
      <postcode>49628-7978</postcode>
      <region>Michigan</region>
      <region_code>Michigan</region_code>
      <region_id xsi:nil="true" />
      <street>
        <string>6146 Honey Bluff Parkway</string>
      </street>
      <telephone>(555) 229-3326</telephone>
      <vat_is_valid xsi:nil="true" />
      <vat_request_date xsi:nil="true" />
      <vat_request_success xsi:nil="true" />
    </billing_address>
    <billing_address_id>2</billing_address_id>
    <can_ship_partially xsi:nil="true" />
    <can_ship_partially_item xsi:nil="true" />
    <created_at>2016-02-01T11:00:50</created_at>
    <customer_dob xsi:nil="true" />
    <customer_email>roni_cost@example.com</customer_email>
    <customer_firstname>Veronica</customer_firstname>
    <customer_gender>0</customer_gender>
    <customer_group_id>1</customer_group_id>
    <customer_id>1</customer_id>
    <customer_is_guest xsi:nil="true" />
    <customer_lastname>Costello</customer_lastname>
    <customer_note_notify xsi:nil="true" />
    <discount_amount>0</discount_amount>
    <discount_canceled xsi:nil="true" />
    <discount_invoiced>0</discount_invoiced>
    <discount_refunded xsi:nil="true" />
    <edit_increment xsi:nil="true" />
    <email_sent xsi:nil="true" />
    <entity_id>1</entity_id>
    <forced_shipment_with_invoice xsi:nil="true" />
    <global_currency_code>GBP</global_currency_code>
    <grand_total>34</grand_total>
    <discount_tax_compensation_amount>0</discount_tax_compensation_amount>
    <discount_tax_compensation_invoiced xsi:nil="true" />
    <discount_tax_compensation_refunded xsi:nil="true" />
    <increment_id>000000001</increment_id>
    <is_virtual>0</is_virtual>
    <items>
      <item>
        <amount_refunded>0</amount_refunded>
        <base_amount_refunded>0</base_amount_refunded>
        <base_cost xsi:nil="true" />
        <base_discount_amount xsi:nil="true" />
        <base_discount_invoiced>0</base_discount_invoiced>
        <base_discount_refunded xsi:nil="true" />
        <base_discount_tax_compensation_amount xsi:nil="true" />
        <base_discount_tax_compensation_invoiced>0</base_discount_tax_compensation_invoiced>
        <base_discount_tax_compensation_refunded xsi:nil="true" />
        <base_original_price xsi:nil="true" />
        <base_price>0</base_price>
        <base_price_incl_tax xsi:nil="true" />
        <base_row_invoiced>0</base_row_invoiced>
        <base_row_total>0</base_row_total>
        <base_row_total_incl_tax xsi:nil="true" />
        <base_tax_amount xsi:nil="true" />
        <base_tax_before_discount xsi:nil="true" />
        <base_tax_invoiced>0</base_tax_invoiced>
        <base_tax_refunded xsi:nil="true" />
        <base_weee_tax_applied_amount xsi:nil="true" />
        <base_weee_tax_applied_row_amnt xsi:nil="true" />
        <base_weee_tax_disposition xsi:nil="true" />
        <base_weee_tax_row_disposition xsi:nil="true" />
        <created_at>2016-02-01T11:00:50</created_at>
        <discount_amount xsi:nil="true" />
        <discount_invoiced>0</discount_invoiced>
        <discount_percent xsi:nil="true" />
        <discount_refunded xsi:nil="true" />
        <event_id xsi:nil="true" />
        <free_shipping>0</free_shipping>
        <gw_base_price xsi:nil="true" />
        <gw_base_price_invoiced xsi:nil="true" />
        <gw_base_price_refunded xsi:nil="true" />
        <gw_base_tax_amount xsi:nil="true" />
        <gw_base_tax_amount_invoiced xsi:nil="true" />
        <gw_base_tax_amount_refunded xsi:nil="true" />
        <gw_id xsi:nil="true" />
        <gw_price xsi:nil="true" />
        <gw_price_invoiced xsi:nil="true" />
        <gw_price_refunded xsi:nil="true" />
        <gw_tax_amount xsi:nil="true" />
        <gw_tax_amount_invoiced xsi:nil="true" />
        <gw_tax_amount_refunded xsi:nil="true" />
        <discount_tax_compensation_amount xsi:nil="true" />
        <discount_tax_compensation_canceled xsi:nil="true" />
        <discount_tax_compensation_invoiced>0</discount_tax_compensation_invoiced>
        <discount_tax_compensation_refunded xsi:nil="true" />
        <is_qty_decimal>0</is_qty_decimal>
        <is_virtual xsi:nil="true" />
        <item_id>1</item_id>
        <locked_do_invoice xsi:nil="true" />
        <locked_do_ship xsi:nil="true" />
        <name>Iris Workout Top-XS-Red</name>
        <no_discount>0</no_discount>
        <order_id>1</order_id>
        <original_price>0</original_price>
        <parent_item_id xsi:nil="true" />
        <price>0</price>
        <price_incl_tax xsi:nil="true" />
        <product_id>1420</product_id>
        <product_type>simple</product_type>
        <qty_backordered xsi:nil="true" />
        <qty_canceled>0</qty_canceled>
        <qty_invoiced>1</qty_invoiced>
        <qty_ordered>1</qty_ordered>
        <qty_refunded>0</qty_refunded>
        <qty_returned xsi:nil="true" />
        <qty_shipped>1</qty_shipped>
        <quote_item_id xsi:nil="true" />
        <row_invoiced>0</row_invoiced>
        <row_total>0</row_total>
        <row_total_incl_tax xsi:nil="true" />
        <row_weight xsi:nil="true" />
        <sku>WS03-XS-Red</sku>
        <store_id>1</store_id>
        <tax_amount xsi:nil="true" />
        <tax_before_discount xsi:nil="true" />
        <tax_canceled xsi:nil="true" />
        <tax_invoiced>0</tax_invoiced>
        <tax_percent xsi:nil="true" />
        <tax_refunded xsi:nil="true" />
        <updated_at>2016-02-01T11:00:51</updated_at>
        <weee_tax_applied_amount xsi:nil="true" />
        <weee_tax_applied_row_amount xsi:nil="true" />
        <weee_tax_disposition xsi:nil="true" />
        <weee_tax_row_disposition xsi:nil="true" />
        <weight>1</weight>
      </item>
    </items>
    <order_currency_code>GBP</order_currency_code>
    <payment>
      <additional_information>
        <string>Check / Money order</string>
        <string xsi:nil="true" />
        <string xsi:nil="true" />
      </additional_information>
      <amount_authorized xsi:nil="true" />
      <amount_canceled xsi:nil="true" />
      <amount_ordered>34</amount_ordered>
      <amount_paid>34</amount_paid>
      <amount_refunded xsi:nil="true" />
      <base_amount_authorized xsi:nil="true" />
      <base_amount_canceled xsi:nil="true" />
      <base_amount_ordered>34</base_amount_ordered>
      <base_amount_paid>34</base_amount_paid>
      <base_amount_paid_online xsi:nil="true" />
      <base_amount_refunded xsi:nil="true" />
      <base_amount_refunded_online xsi:nil="true" />
      <base_shipping_amount>5</base_shipping_amount>
      <base_shipping_captured>5</base_shipping_captured>
      <base_shipping_refunded xsi:nil="true" />
      <entity_id>1</entity_id>
      <method>checkmo</method>
      <parent_id>1</parent_id>
      <quote_payment_id xsi:nil="true" />
      <shipping_amount>5</shipping_amount>
      <shipping_captured>5</shipping_captured>
      <shipping_refunded xsi:nil="true" />
    </payment>
    <payment_authorization_amount xsi:nil="true" />
    <payment_auth_expiration xsi:nil="true" />
    <protect_code>4f9352</protect_code>
    <quote_address_id xsi:nil="true" />
    <quote_id>1</quote_id>
    <shipping_amount>5</shipping_amount>
    <shipping_canceled xsi:nil="true" />
    <shipping_description>Flat Rate - Fixed</shipping_description>
    <shipping_discount_amount>0</shipping_discount_amount>
    <shipping_discount_tax_compensation_amount>0</shipping_discount_tax_compensation_amount>
    <shipping_incl_tax>5</shipping_incl_tax>
    <shipping_invoiced>5</shipping_invoiced>
    <shipping_refunded xsi:nil="true" />
    <shipping_tax_amount>0</shipping_tax_amount>
    <shipping_tax_refunded xsi:nil="true" />
    <state>complete</state>
    <status>complete</status>
    <status_histories>
      <status_history>
        <comment>test</comment>
        <created_at>2016-04-06T15:55:21</created_at>
        <entity_id>2</entity_id>
        <is_customer_notified xsi:nil="true" />
        <is_visible_on_front>0</is_visible_on_front>
        <parent_id>1</parent_id>
        <status>processing</status>
      </status_history>
    </status_histories>
    <store_currency_code>GBP</store_currency_code>
    <store_id>1</store_id>
    <store_name>Main Website
Main Website Store</store_name>
    <store_to_base_rate xsi:nil="true" />
    <store_to_order_rate xsi:nil="true" />
    <subtotal>29</subtotal>
    <subtotal_canceled xsi:nil="true" />
    <subtotal_incl_tax>29</subtotal_incl_tax>
    <subtotal_invoiced>29</subtotal_invoiced>
    <subtotal_refunded xsi:nil="true" />
    <tax_amount>0</tax_amount>
    <tax_canceled xsi:nil="true" />
    <tax_invoiced>0</tax_invoiced>
    <tax_refunded xsi:nil="true" />
    <total_canceled xsi:nil="true" />
    <total_due>0</total_due>
    <total_invoiced>34</total_invoiced>
    <total_item_count>1</total_item_count>
    <total_offline_refunded xsi:nil="true" />
    <total_online_refunded xsi:nil="true" />
    <total_paid>34</total_paid>
    <total_qty_ordered>1</total_qty_ordered>
    <total_refunded xsi:nil="true" />
    <updated_at>2016-04-06T15:55:21</updated_at>
    <weight>1</weight>
    <unique_id>1</unique_id>
  </SalesOrder>
</ArrayOfSalesOrder>
```
