---
slug: uploading-feeds-to-amazon-marketplace
redirect_from: "/article/148-uploading-feeds-to-amazon-marketplace"
title: Uploading Feeds to Amazon Marketplace
---
This task will upload any Amazon XML feed.

## Settings
### API Call Delay
_Required_   
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

### Feed Type
_Required_  
Choose from the list of supported feeds for upload. We support all available types of the Feeds API.

### Input File
_Required_  
The name of the file containing the data feed in XML format.

### Output File
_Optional_  
Optional output for the response of the upload. 

### Zynk Settings
See [Common Task Settings](common-task-settings).