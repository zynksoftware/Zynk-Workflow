---
slug: uploading-orders-to-woocommerce
redirect_from: "/article/340-uploading-orders-to-woocommerce"
title: Uploading Orders to WooCommerce
---
This task will update or insert orders into your WooCommerce store from an XML file. The orders in the input file are matched to orders in WooCommerce based on the `<id>` provided. If a match is found, the existing order in WooCommerce will be updated. If no `<id>` is provided, a new order will be created.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any orders which fail to upload to WooCommerce. Defaults to 'woo_commerce_order_upsert_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the orders to upload to WooCommerce. Defaults to 'woo_commerce_order_upsert.xml'.

### Success File
_Required_  
The name of the XML file to save any orders which successfully uploaded to WooCommerce. Defaults to 'woo_commerce_order_upsert_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent another order with the same `<external_id>` as a previously uploaded record from being uploaded to WooCommerce.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file showing a status update for order ID 9. The file is the same format as the output from the [Downloading Orders from WooCommerce](downloading-orders-from-woocommerce) task. Any fields which are not included in the XML won't be updated, and will keep their current value.
```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderList>
  <orders>
    <order>
      <id>9</id>
      <status>processing</status>
    </order>
  </orders>
</OrderList>
```