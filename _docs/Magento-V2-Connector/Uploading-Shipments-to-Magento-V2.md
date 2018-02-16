---
slug: uploading-shipments-to-magento-v2
redirect_from: "/article/974-uploading-shipments-to-magento"
title: Uploading Shipments to Magento V2
---
This task will create new shipments for existing orders in Magento. See below for a sample input file.

The `<entity_id>` element is used to specify the ID of the order to create the shipment for. If no ID is specified, the task will use the `<external_id>` element in conjunction with Zynk's truth table to look up the ID of an order that has been previously processed by Zynk. If no external ID is provided, the `<increment_id>` element will be used to look up the order ID based on the increment ID of the order.

You can optionally provide a collection of `<item>` elements to ship specific items on the order. If no items are provided, the task will ship all remaining items on the order.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

## Fail File
_Required_  
The XML file to save failed shipment uploads to. The data will be written in the same format as the input file.

## Input File
_Required_  
The XML file containing the shipments to upload in Magento.

## Success File
_Required_  
The XML file to save successful shipment uploads to. The data will be written in the same format as the input file.

## Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. This will create or update the customer with the email address `support@zynk.com`.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfShipment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Shipment>
    <external_id>9814</external_id>
    <order>
      <!-- At least one of the following must be provided to identify the order to ship -->
      <entity_id>4</entity_id>
      <external_id>1</external_id>
      <increment_id>000000004</increment_id>
    </order>
    <!-- If no items collection is provided, all items on the order will be shipped -->
    <items>
      <item>
        <sku>WSH12-32-Purple</sku>
        <qty>1</qty>
      </item>
    </items>
    <tracks>
      <track>
        <track_number>abcd-1234</track_number>
        <title>DHL Next Day Shipping</title>
        <carrier_code>DHL</carrier_code>
      </track>
    </tracks>
    <comment>
      <comment>Leave by the door</comment>
      <is_visible_on_front>1</is_visible_on_front>
    </comment>
  </Shipment>
</ArrayOfShipment>
```
