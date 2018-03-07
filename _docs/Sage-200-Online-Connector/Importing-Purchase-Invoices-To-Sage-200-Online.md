---
slug: importing-purchase-invoices-to-sage-200-online
redirect_from: "/article/importing-purchase-invoices-to-sage-200-online"
title: Importing Purchase Invoices To Sage 200 Online
---
This task will insert new purchase invoices into Sage 200 Online, from an XML file.

## Settings
### Sage 200 Online Connection
_Required_  
The connection to Sage 200 Online to use. See the [Connecting to Sage 200 Online](connecting-to-sage-200-online) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
 The XML file to output any records to which fail to upload to Sage.

### Input File
_Required_  
The XML file containing the records to upload to Sage. See below for a sample input file. 

### Success File
_Required_  
The XML file to output any records to which are successfully uploaded to Sage. 

### Prevent Reprocessing
_Required_  
When set to true this will prevent another record with the same `<external_id>` as a previously uploaded record from being uploaded to Sage.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<PurchaseInvoices xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseInvoice>
    <external_id>523055</external_id>
    <reference>0000000123</reference>
    <second_reference>0000000123</second_reference>
    <transaction_date>2016-05-24T00:00:00</transaction_date>
    <due_date>2016-06-08T00:00:00</due_date>
    <document_goods_value>10.00</document_goods_value>
    <document_tax_value>2.00</document_tax_value>
    <exchange_rate>1.000000</exchange_rate>
    <settled_immediately>false</settled_immediately>
    <discount_days>0</discount_days>
    <supplier>
      <reference>ZYNK0001</reference>
    </supplier>
    <tax_analysis_items>
      <tax_analysis_item>
        <tax_code>
          <code>1</code>
        </tax_code>
        <goods_amount>10</goods_amount>
      </tax_analysis_item>
    </tax_analysis_items>
  </PurchaseInvoice>
</PurchaseInvoices>
```
