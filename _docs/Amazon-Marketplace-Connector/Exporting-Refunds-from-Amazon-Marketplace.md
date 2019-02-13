---
slug: exporting-refunds-from-amazon-marketplace
title: Exporting Refunds from Amazon Marketplace
---
This task will provide a list of refunds, in an XML format.

## Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

### Export Detailed
_Required_  
Set to true to download more detailed information from Amazon.

### Export From
_Required_  
The rolling date to download refunds from. This will automatically update each time the task runs. TIP: If you want to re-download old refunds, change the Download From property

### Order IDs
_Optional_  
If you want to get the refunds for specific orders, enter the order IDs here. If there is more than one ID, they can be provided as a comma separated list.

### Output File
_Required_  
The name of the file to export the downloaded refunds to.

### Zynk Settings
See [Common Task Settings](common-task-settings).