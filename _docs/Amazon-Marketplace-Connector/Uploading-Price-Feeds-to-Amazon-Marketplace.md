---
slug: uploading-price-feeds-to-amazon-marketplace
redirect_from: "/article/150-uploading-price-feeds-to-amazon-marketplace"
title: Uploading Price Feeds to Amazon Marketplace
---
This task will take an XML for CSV file and update your pricing on your Amazon Seller account.

## Amazon Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Channels
_Required_  
Choose at least one marketplace to send the XML feed to. For information about how Amazon handles feeds sent to multiple marketplaces, see [Using Multiple Marketplaces](http://docs.developer.amazonservices.com/en_UK/feeds/Feeds_EU_Global_Seller.html).

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

## Export Settings
### Output File
_Optional_  
Optional output for the response of the upload. 

## Feed Settings
### Input File
_Required_  
The name of the file containing the price data feed.

## Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Amazon Marketplace - Submit Feeds tutorial](amazon-submit-feeds).