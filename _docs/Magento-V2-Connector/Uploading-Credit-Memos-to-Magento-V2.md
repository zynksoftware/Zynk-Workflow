---
slug: uploading-credit-memos-to-magento-v2
redirect_from: "/article/uploading-credit-memos-to-magento-v2"
title: Uploading Credit Memos to Magento V2
---
This task will create new credit memos in Magento. See below for a sample input file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to save failed customer uploads to. The data will be written in the same format as the input file.

### Input File
_Required_  
The XML file containing the customers to upload in Magento.

### Success File
_Required_  
The XML file to save successful customer uploads to. The data will be written in the same format as the input file.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Refund Offline
_Required_  
Set to true to request that refunds are completed offline.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. This shows the minimum amount of information required to create a credit memo in Magento.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo>
  <CreditMemo>
    <order_id>5</order_id>
    <invoice_id>4</invoice_id>
    <subtotal>29</subtotal>
    <subtotal_incl_tax>29</subtotal_incl_tax>
    <tax_amount>0</tax_amount>
    <grand_total>34</grand_total>
    <shipping_amount>5</shipping_amount>
    <base_subtotal>29</base_subtotal>
    <base_subtotal_incl_tax>29</base_subtotal_incl_tax>
    <base_tax_amount>0</base_tax_amount>
    <base_grand_total>34</base_grand_total>
    <base_shipping_amount>5</base_shipping_amount>
    <items>
      <item>
        <order_item_id>5</order_item_id>
        <price>29</price>
        <qty>1</qty>
        <row_total>29</row_total>
        <tax_amount>0</tax_amount>
      </item>
    </items>
    <comments />
  </CreditMemo>
</ArrayOfCreditMemo>
```
