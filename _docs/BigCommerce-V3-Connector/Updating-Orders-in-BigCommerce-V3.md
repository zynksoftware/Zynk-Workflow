---
slug: updating-orders-to-bigcommerce-v3
title: Updating Orders to BigCommerce V3
---
This task will change the status of orders in your BigCommerce store. It can be used in conjunction with the Download Stage setting on the [Downloading Orders from BigCommerce V3](downloading-orders-from-bigcommerce-v3) task, to change the status of orders once they have been processed to prevent them downloading again.

## Settings
### Connection
_Required_  
The BigCommerce connection to use.See the [Connecting to BigCommerce V3](connecting-to-bigcommerce-v3) article if you require more information on how to create/manage connections.

### Notify Stage
_Required_  
The order status to use when updating the orders.

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

These should be stored in the same format as orders downloaded using the 'Download Orders' task, but the only required information is the  `<id>` of the orders.

```xml
<?xml version="1.0" encoding="utf-8"?>
<orders>
  <order>
    <id>105</id>
  </order>
</orders>
```