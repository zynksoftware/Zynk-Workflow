---
slug: downloading-customers-from-shopify
redirect_from: "/article/308-downloading-customers-from-shopify"
title: Downloading Customers from Shopify
---
This task will download a list of customers from your Shopify store, and save them to an XML file.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### From ID
_Required_  
If an ID number is specified, the task will only download customers with an ID number greater than the ID number entered.

### Output File
_Required_  
The XML file to save the list of customers to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<customers type="array">
  <customer>
    <id type="integer">96430088</id>
    <email>support@zynk.com</email>
    <accepts-marketing type="boolean">false</accepts-marketing>
    <first-name>John</first-name>
    <last-name>Smith</last-name>
    <orders-count type="integer">0</orders-count>
    <total-spent type="decimal">0.0</total-spent>
    <note>Update</note>
    <created-at type="datetime">2012-08-16T07:49:39-04:00</created-at>
    <updated-at type="datetime">2012-08-17T07:18:38-04:00</updated-at>
    <state>disabled</state>
    <last-order-id type="integer" nil="true"></last-order-id>
    <tags></tags>
    <last-order-name nil="true"></last-order-name>
    <addresses type="array">
      <address>
        <first-name>John</first-name>
        <last-name>Smith</last-name>
        <address1>Nelson House</address1>
        <address2>Fleming Business Centre</address2>
        <company>Zynk Software</company>
        <city>Newcastle</city>
        <province>Tyne & Wear</province>
        <country>United Kingdom</country>
        <zip>NE2 3AE</zip>
        <phone>0123456789</phone>
        <id type="integer">133155492</id>
        <name>John Smith</name>
        <province-code nil="true"></province-code>
        <country-code>GB</country-code>
        <default type="boolean">true</default>
      </address>
    </addresses>
  </customer>
</customers>
```