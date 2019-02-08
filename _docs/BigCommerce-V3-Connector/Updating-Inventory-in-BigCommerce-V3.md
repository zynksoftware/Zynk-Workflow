---
slug: updating-inventory-to-bigcommerce-v3
title: Updating Inventory to BigCommerce V3
---
This task will update stock levels of products and option SKUs in your BigCommerce store.

## Settings
### Connection
_Required_  
The BigCommerce connection to use.See the [Connecting to BigCommerce V3](connecting-to-bigcommerce-v3) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed uploads to.

### Input File
_Required_  
The XML file containing the product updates. These should be stored in the same format as products downloaded using the 'Download Products' task.

### Success File
_Required_  
The XML file to output successful updates to.

### Prevent Reprocessing
_Required_  
Set to true to only process a record once, or set to false to always update records.  Defaults to False.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.

If you are updating a simple product you can provide `<sku>`, however if you are updating an option you will also need to include details of the parent.  This can either be `<parent_sku>` or `<parent_id>`.

You can set `<inventory_level>` and `<inventory_warning_level>`, as well as `<inventory_tracking>` which can be one of `none`, `product` or `variant`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<inventories>
    <inventory>
        <sku>SAMPLE001</sku>
        <inventory_level>20</inventory_level>
        <inventory_warning_level>5</inventory_warning_level>
        <inventory_tracking>variant</inventory_tracking>
    </inventory>
    <inventory>
        <parent_sku>SAMPLE001</parent_sku>
        <sku>SAMPLE001-BLACK</sku>
        <inventory_level>20</inventory_level>
        <inventory_warning_level>5</inventory_warning_level>
        <inventory_tracking>variant</inventory_tracking>
    </inventory>
</inventories>
```