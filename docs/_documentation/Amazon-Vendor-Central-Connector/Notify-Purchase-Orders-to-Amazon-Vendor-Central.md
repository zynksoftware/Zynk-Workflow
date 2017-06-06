---
slug: notify-purchase-orders-to-amazon-vendor-central
redirect_from: "/article/161-notify-purchase-orders-to-amazon-vendor-central"
title: Notify Purchase Orders to Amazon Vendor Central
---
This task will delete purchase order (ORDERS) files from the Amazon Vendor Central SFTP. Use this task to remove purchase orders once they have been processed successfully, to prevent them from being downloaded again.

## Settings
### Connection
_Required_  
The Amazon Vendor Central Connection to use. See the [Connecting to Amazon Vendor Central](connecting-to-amazon-vendor-central) article if you require more information on how to create/manage connections.

### Filename
_Required_  
The purchase order file to delete from the SFTP. This should be the same file name as output by the [Downloading Purchases from Amazon Vendor Central](downloading-purchases-from-amazon-vendor-central) task.

### Zynk Settings
See [Common Task Settings](common-task-settings).