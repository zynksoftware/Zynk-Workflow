---
slug: importing-orders-to-woocommerce-v3
title: Importing Orders to WooCommerce V3.0+
---
This task will update or insert orders into your WooCommerce store from an XML file. 

The orders in the input file are matched to orders in WooCommerce based on the `<id>` provided. If a match is found, the existing order in WooCommerce will be updated. If no `<id>` is provided, a new order will be created.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce-v3) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any orders which fail to import to WooCommerce. Defaults to 'woo_commerce_import_orders_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the orders to import to WooCommerce. Defaults to 'woo_commerce_import_orders.xml'.

### Success File
_Required_  
The name of the XML file to save any orders which successfully imported to WooCommerce. Defaults to 'woo_commerce_import_orders_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent another order with the same `<external_id>` as a previously imported record from being imported to WooCommerce.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file showing a status update for order ID 9. The file is the same format as the output from the [Export Orders](exporting-orders-from-woocommerce-v3) task. Any fields which are not included in the XML won't be updated, and will keep their current value.
```xml
<?xml version="1.0" encoding="utf-8"?>
<orders>
  <order>
    <id>9</id>
    <external_id>2414</external_id>
    <status>processing</status>
  </order>
</orders>
```