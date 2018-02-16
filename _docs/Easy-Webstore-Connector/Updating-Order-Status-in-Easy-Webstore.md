---
slug: updating-order-status-in-easy-webstore
redirect_from: "/article/209-updating-order-status-in-easy-webstore"
title: Updating Order Status in Easy Webstore
---
This task will update the status of orders in your store. It can be used in conjunction with the Order Status setting on the [Download Orders](downloading-orders-from-easy-webstore) task, to change the status of orders once they have been processed to prevent them downloading again.

## Settings
### Connection
_Required_  
The Easy Webstore connection to use.  See the [Connecting to Easy Webstore](connecting-to-easy-webstore) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed order updates to.

### Input File
_Required_  
The XML file containing the order status updates. The updates should be stored in the same format as orders downloaded using the 'Download Orders' task, but only the `<ID>` and `<Status>` nodes are required for each order.

### Send Alerts
_Required_  
When updating to certain status, emails may be automatically sent to the customer. This can be prevented by, setting this option to False. Defaults to False.

### Success File
_Required_  
The XML file to output successful order updates to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Easy Webstore to Sage 50 Integration](easy-webstore-to-sage-50-integration) article.

Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <ID>2830252</ID>
    <Status>Dispatched</Status>
  </Order>
</ArrayOfOrder>
```