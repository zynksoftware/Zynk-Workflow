---
slug: importing-customers-to-shopify
title: Importing Customers into Shopify
---
This task will import customers into your Shopify store using the customer data in an XML file.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Prevent Reprocessing
_Required_
Optionally prevent reprocessing the same records by providing an <external_id> in the XML you provide.

### Fail File
_Required_  
The XML file to output any failed uploads to.

### Input File
_Required_  
The XML file containing the records. 

### Success File
_Required_  
The XML file to output successful uploads to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<customers type="array">
  <customer>
    <id type="integer">959687688281</id>
    <email>support@zynk.com</email>
    <accepts-marketing type="boolean">false</accepts-marketing>
    <created-at type="dateTime">2018-11-13T08:46:48-05:00</created-at>
    <updated-at type="dateTime">2019-11-07T11:09:19-05:00</updated-at>
    <first-name>Chris</first-name>
    <last-name>Hotchkiss</last-name>
    <orders-count type="integer">3</orders-count>
    <state>disabled</state>
    <total-spent type="decimal">43.00</total-spent>
    <last-order-id type="integer">684838191193</last-order-id>
    <note nil="true" />
    <verified-email type="boolean">true</verified-email>
    <multipass-identifier nil="true" />
    <tax-exempt type="boolean">true</tax-exempt>
    <phone nil="true" />
    <tags></tags>
    <last-order-name>#1003</last-order-name>
    <currency>GBP</currency>
  </customer>
</customers>
```
