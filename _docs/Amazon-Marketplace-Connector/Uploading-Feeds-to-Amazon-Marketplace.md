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

## Example
A sample input file is shown below. This contains data for the '_POST_PRODUCT_DATA_' feed type.

```xml
<?xml version="1.0" encoding="utf-8"?>
<AmazonEnvelope xsi:noNamespaceSchemaLocation="amzn-envelope.xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Header>
    <DocumentVersion>1.01</DocumentVersion>
    <MerchantIdentifier>M_IDENTIFIER_1234567</MerchantIdentifier>
  </Header>
  <MessageType>Product</MessageType>
  <Message>
    <MessageID>1</MessageID>
    <OperationType>PartialUpdate</OperationType>
    <Product>
      <SKU>TEST001</SKU>
      <StandardProductID>
        <Type>EAN</Type>
        <Value>019965809665</Value>
      </StandardProductID>
      <Condition>
        <ConditionType>New</ConditionType>
      </Condition>
      <DescriptionData>
        <Title>China Glaze Ahoy Nail Polish Lacquer with Hardeners 14ml</Title>
        <Brand>China Glaze</Brand>
        <Manufacturer>China Glaze</Manufacturer>
      </DescriptionData>
    </Product>
  </Message>
</AmazonEnvelope>
```
