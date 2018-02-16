---
slug: downloading-orders-from-ekm-powershop
redirect_from: "/article/218-downloading-orders-from-ekm-powershop"
title: Downloading Orders from EKM Powershop
---
This task will download all orders that have been modified since the last data specified, to an XML file.

## Settings
### Connection
_Required_  
The EKM Powershop connection to use.  See the [Connecting to EKM Powershop](connecting-to-ekm-powershop) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all orders, or false to only download new orders since this task last ran.

### Order Details
_Required_  
Set to true to download full details about each order (may be slow if there are many orders to download). Set to false to download only basic information on each order.

### Output File
_Required_  
The name of the XML file to export the data to.

### Zynk Settings
See [Common Task Settings](common-task-settings)