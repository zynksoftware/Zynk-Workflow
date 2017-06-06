---
slug: downloading-credit-memos-from-magento
redirect_from: "/article/259-downloading-credit-memos-from-magento"
title: Downloading Credit Memos from Magento
---
This task will download credit memos from Magento in Magento XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Download Status
_Required_  
The status to filter the credit memos on.

### Download All
_Required_  
Set to true to download all credit memos which match the filter, or false to also filter on new/modified credit memos.

### Download From
_Required_  
The rolling date the download new/modified credit memos from.

### Start Date
_Optional_  
Any credit memos created before this date will be ignored, even if they are modified.

### Output File
_Required_  
The name of the file to export the credit memos to.

### Filter Property
_Optional_  
The property the filter is to be based upon. The property name should match the API field name, as seen in the output file.

### Filter Type
_Optional_  
The following types of filter are available:

* __eq__ - Returns records where the property matches the specified value
* __gt__ - Returns records where the property is greater than the specified value
* __lt__ - Returns records where the property is less than the specified value.
* __like__ - Returns records where the property contains the specified value.
* __isnull__ - Returns records where the property is null.
* __notnull__ - Returns records where the property is not null.

### Filter Value
_Optional_  
The value the filter is to be based upon. When using the eq filter type, you can specify multiple values by separating them with commas, or using the 'Use a list' option after clicking the ellipsis (...) button.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0"?>
<ArrayOfCreditMemoInfo>
  <CreditMemoInfo>
    <Fields>
      <Field Name="adjustment_positive" Value="0.0000" />
      <Field Name="base_adjustment_negative" Value="0.0000" />
      <Field Name="base_subtotal_incl_tax" Value="10.0000" />
      <Field Name="subtotal_incl_tax" Value="10.0000" />
      <Field Name="adjustment_negative" Value="0.0000" />
      <Field Name="base_adjustment" Value="0.0000" />
      <Field Name="adjustment" Value="0.0000" />
      <Field Name="base_adjustment_positive" Value="0.0000" />
      <Field Name="hidden_tax_amount" Value="0.0000" />
      <Field Name="base_hidden_tax_amount" Value="0.0000" />
      <Field Name="shipping_hidden_tax_amount" Value="" />
      <Field Name="base_shipping_hidden_tax_amnt" Value="" />
      <Field Name="shipping_incl_tax" Value="5.0000" />
      <Field Name="base_shipping_incl_tax" Value="5.0000" />
      <Field Name="creditmemo_id" Value="1" />
      <Field Name="order_increment_id" Value="100000001" />
      <Field Name="comments" Value="" />
    </Fields>
    <store_id>1</store_id>
    <base_shipping_tax_amount>0.0000</base_shipping_tax_amount>
    <store_to_order_rate>1.0000</store_to_order_rate>
    <base_discount_amount>0.0000</base_discount_amount>
    <base_to_order_rate>1.0000</base_to_order_rate>
    <grand_total>15.0000</grand_total>
    <shipping_amount>5.0000</shipping_amount>
    <base_shipping_amount>5.0000</base_shipping_amount>
    <store_to_base_rate>1.0000</store_to_base_rate>
    <base_to_global_rate>1.0000</base_to_global_rate>
    <base_subtotal>10.0000</base_subtotal>
    <discount_amount>0.0000</discount_amount>
    <subtotal>10.0000</subtotal>
    <base_grand_total>15.0000</base_grand_total>
    <base_tax_amount>0.0000</base_tax_amount>
    <shipping_tax_amount>0.0000</shipping_tax_amount>
    <tax_amount>0.0000</tax_amount>
    <order_id>1</order_id>
    <state>2</state>
    <shipping_address_id>2</shipping_address_id>
    <billing_address_id>1</billing_address_id>
    <store_currency_code>GBP</store_currency_code>
    <order_currency_code>GBP</order_currency_code>
    <base_currency_code>GBP</base_currency_code>
    <global_currency_code>GBP</global_currency_code>
    <increment_id>100000001</increment_id>
    <created_at>2014-04-22 10:18:07</created_at>
    <updated_at>2014-04-22 10:18:07</updated_at>
    <items>
      <CreditMemoProduct>
        <Fields>
          <Field Name="price_incl_tax" Value="10.0000" />
          <Field Name="base_price_incl_tax" Value="10.0000" />
          <Field Name="base_row_total_incl_tax" Value="10.0000" />
          <Field Name="row_total_incl_tax" Value="10.0000" />
          <Field Name="hidden_tax_amount" Value="0.0000" />
          <Field Name="base_hidden_tax_amount" Value="0.0000" />
          <Field Name="base_weee_tax_applied_row_amnt" Value="0.0000" />
        </Fields>
        <product_id>1</product_id>
        <sku>ABC</sku>
        <name>test</name>
        <price>10.0000</price>
        <qty>1.0000</qty>
        <item_id>1</item_id>
        <parent_id>1</parent_id>
        <weee_tax_applied_row_amount>0.0000</weee_tax_applied_row_amount>
        <base_price>10.0000</base_price>
        <base_weee_tax_row_disposition>0.0000</base_weee_tax_row_disposition>
        <tax_amount>0.0000</tax_amount>
        <base_weee_tax_applied_amount>0.0000</base_weee_tax_applied_amount>
        <weee_tax_row_disposition>0.0000</weee_tax_row_disposition>
        <base_row_total>10.0000</base_row_total>
        <row_total>10.0000</row_total>
        <weee_tax_applied_amount>0.0000</weee_tax_applied_amount>
        <base_weee_tax_disposition>0.0000</base_weee_tax_disposition>
        <base_tax_amount>0.0000</base_tax_amount>
        <weee_tax_disposition>0.0000</weee_tax_disposition>
        <base_weee_tax_applied_row_amount>0.0000</base_weee_tax_applied_row_amount>
        <order_item_id>1</order_item_id>
        <weee_tax_applied>a:0:{}</weee_tax_applied>
      </CreditMemoProduct>
    </items>
  </CreditMemoInfo>
</ArrayOfCreditMemoInfo>
```