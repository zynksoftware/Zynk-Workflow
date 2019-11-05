---
slug: importing-products-to-woocommerce-v3
title: Importing Products to WooCommerce V3.0+
---
This task will update or insert products into your WooCommerce store from an XML file. The products in the input file are matched to products in WooCommerce based on the `<id>` or the `<sku>`. If an `<id>` is provided, the existing product in WooCommerce with this ID will be updated. If a `<sku>` is provided and a product already exists in WooCommerce with a matching SKU, the existing product will be updated. Otherwise a new product will be created.

Please note the `<id>` must be provided to update existing draft products. Due to a limitation of the WooCommerce API, it is not possible to match draft products based on SKU.

## Settings
### Connection
_Required_  
The WooCommerce connection to use. See the [Connecting to WooCommerce](connecting-to-woocommerce-v3) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any products which fail to import to WooCommerce. Defaults to 'woo_commerce_import_products_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the products to import to WooCommerce. Defaults to 'woo_commerce_import_products.xml'.

### Success File
_Required_  
The name of the XML file to save any products which successfully imported to WooCommerce. Defaults to 'woo_commerce_import_products_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent another product with the same `<external_id>` as a previously imported record from being imported to WooCommerce.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file showing a price and stock level update for the product with SKU 'ABC123' is shown below. The file is the same format as the output from the [Export Products](exporting-products-from-woocommerce-v3) task. Any fields which are not included in the XML won't be updated, and will keep their current value.
```xml
<?xml version="1.0" encoding="utf-8"?>
<products>
  <product>
    <sku>ABC123</sku>
    <regular_price>10.00</regular_price>
    <manage_stock>true</manage_stock>
    <stock_quantity>88</stock_quantity>
    <in_stock>true</in_stock>
  </product>
</products>
```
