---
slug: updating-orders-in-corecommerce
redirect_from: "/article/190-updating-orders-in-corecommerce"
title: Updating Orders in CoreCommerce
---
This task will update the status of orders in CoreCommerce. It can be used in conjunction with the [Downloading Orders from CoreCommerce](downloading-orders-from-corecommerce) task to change the status of orders once they have been successfully processed.

## Settings
### Connection
_Required_  
The CoreCommerce connection to use. See the [Connecting to CoreCommerce](connecting-to-corecommerce) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The file to save any failed order status updates to.

### Input File
_Required_  
The file containing the orders to change the status of. The data must be in the CoreCommerce XML format, an example is shown below.

### Success File
_Required_  
The file to save successful order status updates to.

### Order Status
_Required_  
Select the new status to set the orders to. The following options are available:

* ORDER\_STATUS\_PENDING
* ORDER\_STATUS\_APPROVED
* ORDER\_STATUS\_PARTIALLY\_SHIPPED
* ORDER\_STATUS\_SHIPPED
* ORDER\_STATUS\_PROCESSING
* ORDER\_STATUS\_BACKORDER
* ORDER\_STATUS\_DECLINED
* ORDER\_STATUS\_REFUNDED
* ORDER\_STATUS\_RMA
* ORDER\_STATUS\_VOID
* ORDER\_STATUS\_PAID


### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
 You can find an example of how to use this task in the [Core Commerce to Sage 50 Integration](core-commerce-to-sage-50-integration) article.

Sample input file, which will update the status of order ID 55 and 70:
```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderList>
	<Order id="55" />
	<Order id="70" />
</OrderList>
```

Sample success file, showing that order ID 55 was updated:
```xml
<?xml version="1.0"?>
<OrderResponseList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Order id="55">
		<Code>100</Code>
		<Message />
	</Order>
</OrderResponseList>
```

Sample fail file, showing that order ID 70 was not updated, because it does not exist:
```xml
<?xml version="1.0"?>
<OrderResponseList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Order id="70">
		<Code>801</Code>
		<Message>The order ID referenced does not exist.</Message>
	</Order>
</OrderResponseList>
```