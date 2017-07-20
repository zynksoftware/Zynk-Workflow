---
slug: volo-order-history-xml
title: Volo Order History XML
---
The [Importing Order History into Volo](importing-order-history-into-volo) task allows you to add order history entries to existing orders in Volo. The XML format required for the Input File is described below. Any fields not documented below are not directly supported with our imports.

Sample XML for creating an order history entry:

```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderHistories>
  <OrderHistory>
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

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create an order history entry. The whole structure of the XML schema is used below as a reference of where fields should be in the object model.

## Order History
The `<OrderHistory>` element represents an order and the history entries to create against it in Volo.

| Volo Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | externalId | 7539 | string | 255 | Optional | The ID of the corresponding order from the external system. Used in conjunction with the 'Prevent Reprocessing' setting on the task. |
| Order Number | espOrderNo | 1009 | int | - | Required | The order number must already exist in Volo. |
| - | historyEntries | - | array | - | Required | The list of history entries to add to the order. See below for details. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderHistories>
  <OrderHistory>
    <externalId>7539</externalId>
    <espOrderNo>1009</espOrderNo>
    <historyEntries>
      <!-- See below -->
    </historyEntries>
  </OrderHistory>
</OrderHistories>
```

## History Entry 
The `<HistoryEntry>` element represents an individual history entry to add to an order in Volo. It will appear in Volo on the 'Order History/Notes' tab when viewing a sales order.

| Volo Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Description | description | This is a note. | string | - | Optional |  |
| Type | type | NOTE | enum | - | Optional | Available values: <!--- these are not currently supported by the API but can be added once supported - 'ORDER_IN', 'ORDER_OUT', 'EMAIL', , 'PRINTED', 'PAYMENT', 'UPDATE', 'SCANNED', 'POSTED', 'FAILED_POSTING', 'FEEDBACK', 'PUT_ON_HOLD', 'TAKE_OFF_HOLD', 'BACK_ORDER_ALLOCATED', 'SPLIT_ORDER', 'SIGNATURE', 'FLAG_AMENDMENT', 'QUESTION_ANSWERED', 'QUESTION_RECEIVED' --> 'NOTE'|
| User | username | john.smith | string | - | Optional |  |
| Date | timestamp | 2017-01-01T00:00:00 | datetime | - | Optional | The date should be in XSD format. If not specified, it will default to the current date/time. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderHistories>
  <OrderHistory>
    <historyEntries>
      <historyEntry>
        <description>This is a note.</description>
        <type>NOTE</type>
        <username>john.smith</username>
        <timestamp>2017-01-01T00:00:00</timestamp>
      </historyEntry>
    </historyEntries>
  </OrderHistory>
</OrderHistories>
```
