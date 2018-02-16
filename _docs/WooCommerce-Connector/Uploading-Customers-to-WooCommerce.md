---
slug: uploading-customers-to-woocommerce
redirect_from: "/article/339-uploading-customers-to-woocommerce"
title: Uploading Customers to WooCommerce
---
This task will update or insert customers into your WooCommerce store from an XML file. The customers in the input file are matched to customers in WooCommerce based on the `<id>` or the `<email>`. If an `<id>` is provided, the existing customer in WooCommerce with this ID will be updated. If an `<email>` is provided and a customer already exists in WooCommerce with a matching email, the existing customer will be updated. Otherwise a new customer will be created.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any customers which fail to upload to WooCommerce. Defaults to 'woo_commerce_customer_upsert_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the customers to upload to WooCommerce. Defaults to 'woo_commerce_customer_upsert.xml'.

### Success File
_Required_  
The name of the XML file to save any customers which successfully uploaded to WooCommerce. Defaults to 'woo_commerce_customer_upsert_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent another customer with the same `<external_id>` as a previously uploaded record from being uploaded to WooCommerce.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file showing an update for the customer with email address ' support@zynk.com' is shown below. The file is the same format as the output from the [Downloading Customers from WooCommerce](downloading-customers-from-woocommerce) task. Any fields which are not included in the XML won't be updated, and will keep their current value.
```xml
<?xml version="1.0" encoding="utf-8"?>
<CustomerList>
  <customers>
    <customer>
      <email>support@zynk.com</email>
      <first_name>Adam</first_name>
      <last_name>Wardle</last_name>
      <username>admin</username>
      <billing_address>
        <first_name>Adam</first_name>
        <last_name>Wardle</last_name>
        <company>Zynk Software Ltd</company>
        <address_1>Nelson House</address_1>
        <address_2 />
        <city>Jesmond</city>
        <state>Tyne & Wear</state>
        <postcode>NE2 3AE</postcode>
        <country>GB</country>
        <email>support@zynk.com</email>
        <phone>08451232920</phone>
      </billing_address>
      <shipping_address>
        <first_name>Adam</first_name>
        <last_name>Wardle</last_name>
        <company>Zynk Software Ltd</company>
        <address_1>Nelson House</address_1>
        <address_2 />
        <city>Jesmond</city>
        <state>Tyne & Wear</state>
        <postcode>NE2 3AE</postcode>
        <country>GB</country>
      </shipping_address>
    </customer>
  </customers>
</CustomerList>
```