---
slug: uploading-credit-memos-to-magento
title: Uploading Credit Memos to Magento
---
This task will create new credit memos for existing orders in Magento. The order must have already been invoiced. The task does not support updating existing credit memos.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed credit memo uploads to.

### Input File
_Required_  
The XML file containing the credit memos to upload to Magento.

### Success File
_Required_  
The XML file to output successful credit memo uploads to. 

### Comment
_Optional_  
The comment to include on your credit memo.

### Include Comment
_Required_  
Set to true to add the text specified in the 'Comment' setting as a comment on the credit memos created. Set to false to not add a comment to the credit memos.

### Notify Customer
_Required_  
Set to true to instruct Magento to notify the customer of their credit memo via email. The content and formatting of the email is controlled by Magento.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file, showing a credit memo for a single product and the shipping charge:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <CreditMemo>
    <external_id>cred001</external_id>
    <store_id>1</store_id>
    <shipping_amount>5.0000</shipping_amount>
    <base_shipping_amount>5.0000</base_shipping_amount>
    <discount_amount>0.0000</discount_amount>
    <shipping_address_id>12</shipping_address_id>
    <billing_address_id>11</billing_address_id>
    <store_currency_code>GBP</store_currency_code>
    <order_currency_code>GBP</order_currency_code>
    <base_currency_code>GBP</base_currency_code>
    <global_currency_code>GBP</global_currency_code>
    <order_increment_id>100000011</order_increment_id>
    <items>
      <CreditMemoProduct>
        <product_id>1</product_id>
        <sku>TEST001</sku>
        <name>Test Product</name>
        <price>15.0000</price>
        <qty>1.0000</qty>
        <order_item_id>9</order_item_id>
      </CreditMemoProduct>
    </items>
  </CreditMemo>
</ArrayOfCreditMemo>
```