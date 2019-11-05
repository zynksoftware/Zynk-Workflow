---
slug: importing-customers-to-woocommerce-v3
title: Importing Customers to WooCommerce V3.0+
---
This task will update or insert customers into your WooCommerce store from an XML file. 

The customers in the input file are matched to customers in WooCommerce based on the `<id>` or the `<email>`. If an `<id>` is provided, the existing customer in WooCommerce with this ID will be updated. If an `<email>` is provided and a customer already exists in WooCommerce with a matching email, the existing customer will be updated. Otherwise a new customer will be created.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce-v3) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any customers which fail to import to WooCommerce. Defaults to 'woo_commerce_import_customers_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the customers to import to WooCommerce. Defaults to 'woo_commerce_import_customers.xml'.

### Success File
_Required_  
The name of the XML file to save any customers which successfully imported to WooCommerce. Defaults to 'woo_commerce_import_customers_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent another customer with the same `<external_id>` as a previously imported record from being imported to WooCommerce.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file showing an update for the customer with email address 'support@zynk.com' is shown below. The file is the same format as the output from the [Export Customers](exporting-customers-from-woocommerce-v3) task. Any fields which are not included in the XML won't be updated, and will keep their current value.
```xml
<?xml version="1.0" encoding="utf-8"?>
<customers>
  <customer>
    <email>support@zynk.com</email>
    <first_name>Adam</first_name>
    <last_name>Wardle</last_name>
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
  </customer>
</customers>
```