---
slug: exporting-customers-from-woocommerce-v3
title: Exporting Customers from WooCommerce V3.0+
---
This task will export customers from your WooCommerce store to an XML file.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce-v3) article if you require more information on how to create/manage connections.

### Export Setting > Date Created
_Required_  
The date to export customers from when the task is set to export new records. Updates automatically each time a customer is exported.

### Export Setting > Date Modified
_Required_  
The date to export customers from when the task is set to export modified records. Updates automatically each time a customer is exported.

### Export Setting > Export Modified, New or All Records
_Required_  
Choose which customers should be exported from WooCommerce. The available options are:

* __Modified__ - Exports all customers then only outputs those updated since the date shown in the Date Modified setting. Using this option is likely to cause the task to take a long time to run and result in a large number of API requests.
* __New__ - Exports all customers then only outputs those created since the date shown in the Date Created setting. Using this option is likely to cause the task to take a long time to run and result in a large number of API requests.
* __All__ - Exports all customers.

### Page Size
_Required_  
The number of customers to export per page. Increasing this value will speed up the export, but will consume more memory. Defaults to 10.

### Record IDs
_Optional_  
Enter a comma separated list of IDs of specific records to export. This will override the Export Settings.

### Output File
_Required_  
The name of the XML file to export the customers to. Defaults to 'woo_commerce_export_customers.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customer>
    <id>1</id>
    <date_created>2017-05-24T14:50:52</date_created>
    <date_created_gmt>2017-05-24T13:50:52</date_created_gmt>
    <date_modified>2017-05-24T17:13:42</date_modified>
    <date_modified_gmt>2017-05-24T16:13:42</date_modified_gmt>
    <email>support@zynk.com</email>
    <first_name>Adam</first_name>
    <last_name>Wardle</last_name>
    <role>customer</role>
    <username>admin</username>
    <billing>
      <first_name>Adam</first_name>
      <last_name>Wardle</last_name>
      <company>Zynk Software Ltd</company>
      <address_1>Nelson House</address_1>
      <address_2 />
      <city>Jesmond</city>
      <state>Tyne &amp; Wear</state>
      <postcode>NE2 3AE</postcode>
      <country>GB</country>
      <email>support@zynk.com</email>
      <phone>08451232920</phone>
    </billing>
    <shipping>
      <first_name>Adam</first_name>
      <last_name>Wardle</last_name>
      <company>Zynk Software Ltd</company>
      <address_1>Nelson House</address_1>
      <address_2 />
      <city>Jesmond</city>
      <state>Tyne &amp; Wear</state>
      <postcode>NE2 3AE</postcode>
      <country>GB</country>
    </shipping>
    <meta_data>
      <meta>
        <id>82</id>
        <key>wc_last_active</key>
        <value>1568764800</value>
      </meta>
    </meta_data>
  </customer>
</customers>
```