---
slug: importing-feeds-to-amazon-marketplace
title: Importing Feeds to Amazon Marketplace
---
This task encapsulates the whole process of submitting XML feeds to Amazon, waiting for Amazon to process them, and retrieving the results.

## Settings
### API Call Delay
_Required_   
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Channels
_Required_  
Choose at least one marketplace to send the XML feed to. For information about how Amazon handles feeds sent to multiple marketplaces, see [Using Multiple Marketplaces](http://docs.developer.amazonservices.com/en_UK/feeds/Feeds_EU_Global_Seller.html).

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

### Feed Type
_Required_  
Choose from the list of supported feeds for upload. We support all available types of the Feeds API.

### Fail File
_Required_  
The name of the file to write failed records to. This will be written in the same XML format as the input file.

### Input File
_Required_  
The name of the file containing the data feed in XML format.

### Success File
_Required_  
The name of the file to write successfully processed records to. This will be written in the same XML format as the input file.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. This contains data for the '_POST_PRODUCT_DATA_' feed type.

Documentation for Amazon's XML feed formats can be found in [Selling on Amazon Guide to XML](https://images-na.ssl-images-amazon.com/images/G/01/rainier/help/XML_Documentation_Intl.pdf).

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
