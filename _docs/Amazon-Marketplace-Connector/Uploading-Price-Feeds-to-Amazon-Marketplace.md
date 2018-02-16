---
slug: uploading-price-feeds-to-amazon-marketplace
redirect_from: "/article/150-uploading-price-feeds-to-amazon-marketplace"
title: Uploading Price Feeds to Amazon Marketplace
---
This task will take an XML for CSV file and update your pricing on your Amazon Seller account.

## Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

### Input File
_Required_  
The name of the file containing the price data feed.

### Output File
_Optional_  
Optional output for the response of the upload. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Amazon Marketplace - Submit Feeds tutorial](amazon-submit-feeds).