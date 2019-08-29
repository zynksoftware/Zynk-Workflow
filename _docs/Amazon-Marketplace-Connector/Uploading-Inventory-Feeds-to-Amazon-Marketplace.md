---
slug: uploading-inventory-feeds-to-amazon-marketplace
redirect_from: "/article/149-uploading-inventory-feeds-to-amazon-marketplace"
title: Uploading Inventory Feeds to Amazon Marketplace
---
This task will take an XML for CSV file and update your inventory on your Amazon Seller account.

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
Optional output for the response of the upload

## Feed Settings
### Input File
_Required_  
The name of the file containing the inventory data feed.

## Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Amazon Marketplace - Submit Feeds tutorial](amazon-submit-feeds). A sample input file is shown below.

```xml
<?xml version="1.0" encoding="utf-8"?>
<AmazonEnvelope xsi:noNamespaceSchemaLocation="amzn-envelope.xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Header>
    <DocumentVersion>1.01</DocumentVersion>
    <MerchantIdentifier>XXXXXXXXXXXX</MerchantIdentifier>
  </Header>
  <MessageType>Inventory</MessageType>
  <Message>
    <MessageID>1</MessageID>
    <OperationType>Update</OperationType>
    <Inventory>
      <SKU>PROD001</SKU>
      <Quantity>12</Quantity>
    </Inventory>
  </Message>
  <Message>
    <MessageID>2</MessageID>
    <OperationType>Update</OperationType>
    <Inventory>
      <SKU>PROD002</SKU>
      <Quantity>5</Quantity>
    </Inventory>
  </Message>
</AmazonEnvelope>
```
