---
slug: importing-order-history-into-volo
title: Importing Order History into Volo
---
This task will add order history entries to existing orders in Volo, based on an XML file.

## Settings
### Connection
_Required_  
The Volo connection to use. See the [Connecting to Volo](connecting-to-volo) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any order history which failed to import into Volo. Defaults to 'volo_import_order_history_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the order history to import into Volo. Defaults to 'volo_import_order_history.xml'.

### Success File
_Required_  
The name of the XML file to save any order history which was successfully imported into Volo. Defaults to 'volo_import_order_history_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent order history with the same `<externalId>` as a previously imported record from being imported into Volo again.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file showing a note being added to order 1009. See [Volo Order History XML](volo-order-history-xml) for more detailed information.
```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderHistories>
  <OrderHistory>
    <externalId>7539</externalId>
    <espOrderNo>1009</espOrderNo>
    <historyEntries>
      <historyEntry>
        <description>This is a note.</description>
        <type>NOTE</type>
        <username>john.smith</username>
      </historyEntry>
    </historyEntries>
  </OrderHistory>
</OrderHistories>
```