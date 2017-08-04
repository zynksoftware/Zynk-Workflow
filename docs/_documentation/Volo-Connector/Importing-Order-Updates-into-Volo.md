---
slug: importing-order-updates-into-volo
title: Importing Order Updates into Volo
---
This task will update existing orders in Volo, based on an XML file.

## Settings
### Connection
_Required_  
The Volo connection to use. See the [Connecting to Volo](connecting-to-volo) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any order updates which failed to import into Volo. Defaults to 'volo_import_order_updates_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the order updates to import into Volo. Defaults to 'volo_import_order_updates.xml'.

### Success File
_Required_  
The name of the XML file to save any order updates which were successfully imported into Volo. Defaults to 'volo_import_order_updates_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent order updates with the same `<externalId>` as a previously imported record from being imported into Volo again.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file showing an update for order 1009. See [Volo Order Update XML](volo-order-update-xml) for more detailed information.
```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderUpdates>
  <OrderUpdate>
    <externalId>7539</externalId>
    <espOrderNo>1009</espOrderNo>
    <orderStatus>DELIVERED</orderStatus>
    <onHoldNotes>On hold note</onHoldNotes>
    <courier>DHL</courier>
    <courierService>Next Day</courierService>
    <courierTracking>01824-01423</courierTracking>
    <notes>A note<notes>
    <flag1>Red Flag</flag1>
    <flag2>Green Flag</flag2>
    <payments>
      <payment>
        <paymentId>4</paymentId>
        <postedBatchId>1234</postedBatchId>
      </payment>
    </payments>
  </OrderUpdate>
</OrderUpdates>
```