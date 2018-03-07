---
slug: importing-sales-payments-to-sage-200-online
redirect_from: "/article/importing-sales-payments-to-sage-200-online"
title: Importing Sales Payments To Sage 200 Online
---
This task will insert new sales payments into Sage 200 Online, from an XML file.

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
<SalesPayments xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesPayment>
    <external_id>67858</external_id>
    <reference>0000000123</reference>
    <second_reference>0000000123</second_reference>
    <transaction_date>2016-05-24T00:00:00</transaction_date>
    <cheque_value>12.00</cheque_value>
    <exchange_rate>1.000000</exchange_rate>
    <settlement_discount_value>0</settlement_discount_value>
    <bank>
      <code>DEFAULT</code>
    </bank>
    <customer>
      <reference>ZYNK0001</reference>
    </customer>
    <nominal_analysis_items>
      <nominal_analysis_item>
        <code>4000</code>
        <value>12</value>
      </nominal_analysis_item>
    </nominal_analysis_items>
  </SalesPayment>
</SalesPayments>
```
