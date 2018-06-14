---
slug: uploading-shipments-to-magento
redirect_from: "/article/518-uploading-shipments-to-magento"
title: Uploading Shipments to Magento
---
This task will upload shipments to existing orders in Magento. Optionally, you can provide a list of specific items and quantities to ship, or just provide the order number and the task will automatically ship all items. Optionally, you can process the order further by creating an invoice, and processing a payment against that invoice.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed shipment uploads to.

### Input File
_Required_  
The XML file containing the shipments to upload to Magento.

### Success File
_Required_  
The XML file to output successful shipment uploads to. 

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0"?>
<ArrayOfShipment>
  <Shipment> <!-- full shipment -->
    <order_increment_id>100000009</order_increment_id>
    <capture>false</capture> <!-- set to true to create an invoice and process payment -->
  </Shipment>
  <Shipment> <!-- partial shipment -->
    <order_increment_id>100000016</order_increment_id>
    <capture>false</capture> <!-- set to true to create an invoice and process payment -->
    <shipping_info>
      <items>
        <Product>
          <sku>BOARD001</sku>
          <qty>1</qty>
        </Product>
      </items>
    </shipping_info>
    <add_tracks>true</add_tracks>
    <tracks>
      <track>
        <carrier>DHL</carrier>
        <title>DHL</title>
        <track_number>1234567890</track_number>
      </track>
    </tracks>
  </Shipment>
</ArrayOfShipment>
```
