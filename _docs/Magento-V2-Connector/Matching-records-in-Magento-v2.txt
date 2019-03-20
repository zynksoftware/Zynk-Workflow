---
slug: matching-records-in-magento-v2
title: Matching records in Magento v2
---
When attempting to update records in Magento v2 you can provide a <field> and <value> in a match object to try and return a matching record. 

For example, if I wanted to match customers between Magento v2 and Sage 50 based on a custom field called 'sage_account_number' I could provide the following data:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
	<match>
		<field>sage_account_number</field>
		<value>ZYNK0001</value>
	</match>
    <group_id>1</group_id>
    <dob xsi:nil="true" />
    <email>support@zynk.com</email>
    <firstname>Adam</firstname>
    <lastname>Wardle</lastname>
    <gender>0</gender>
    <store_id>1</store_id>
    <website_id>1</website_id>
    <addresses>
      <address>
        <region>
          <region>Tyne &amp; Wear</region>
        </region>
        <country_id>GB</country_id>
        <street>
          <string>Nelson House</string>
          <string>Jesmond</string>
        </street>
        <telephone>214153215</telephone>
        <postcode>NE2 3AE</postcode>
        <city>Newcastle</city>
        <firstname>Adam</firstname>
        <lastname>Wardle</lastname>
        <default_billing>true</default_billing>
        <default_shipping>true</default_shipping>
      </address>
    </addresses>
  </Customer>
</ArrayOfCustomer>
```