---
slug: updating-purchase-orders-in-sage-200
redirect_from: "/article/676-updating-purchase-orders-in-sage-200"
title: Updating Purchase Orders in Sage 200
---
This task will allow you to update existing purchase orders within Sage 200 from our Zynk XML format.  To match existing records you can lookup based on the document number, customer document number or the external id of the order if one was provided from when the order was imported with Zynk.  With the task you can update the received or returned status of order items.


## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed purchase order udpates in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully updated purchase orders in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Further information and sample XML files can be found [Sage 200 Update Purchase Order XML](sage-200-update-purchase-order-xml).