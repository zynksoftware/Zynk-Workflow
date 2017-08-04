---
slug: volo-order-update-xml
title: Volo Order Update XML
---
The [Importing Order Updates into Volo](importing-order-updates-into-volo) task allows you to update existing orders in Volo. The XML format required for the Input File is described below. Any fields not documented below are not directly supported with our imports.

Sample XML for creating an order history entry:

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

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to update an order. The whole structure of the XML schema is used below as a reference of where fields should be in the object model.

## Order Update 
The `<OrderUpdate>` element represents an order and the fields to update against it in Volo.

| Volo Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | externalId | 7539 | string | 255 | Optional | The ID of the corresponding order from the external system. Used in conjunction with the 'Prevent Reprocessing' setting on the task. |
| Order Number | espOrderNo | 1009 | int | - | Required | The order number must already exist in Volo. |
| Status | orderStatus | DELIVERED | enum | - | Optional | Available values: WAITING_FOR_DELIVERY, DELIVERED, CANCELLED, ON_HOLD |
| Order History/Notes | onHoldNotes | On hold note | string | - | Optional | Only applicable when the status is ON_HOLD |
| Payment/Shipping > Courier | courier | DHL | string | - | Optional |  |
| Consignment > Service | courierService | Next Day | string | - | Optional |  |
| Consignment > Number | courierTracking | 01824-01423 | string | - | Optional |  |
| Payment/Shipping > Memo | notes | A note | string | - | Optional |  |
| Flag 1 | flag1 | Red Flag | string | - | Optional |  |
| Flag 2 | flag2 | Green Flag | string | - | Optional |  |
| Payment/Shipping > Payments | payments | - | array | - | Optional | The list of payments to update on the order. See below for details. |

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
      <!-- See below -->
    </payments>
  </OrderUpdate>
</OrderUpdates>
```

## Payment 
The `<Payment>` element represents an update for an existing payment on the order in Volo.

| Volo Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | paymentId | 4 | int | - | Required | The payment ID can be found via the [Exporting Sales Orders from Volo](exporting-sales-orders-from-volo) task. |
| Payment/Shipping > Posted | postedBatchId | 1234 | int | - | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderUpdates>
  <OrderUpdate>
    <payments>
      <payment>
        <paymentId>4</paymentId>
        <postedBatchId>1234</postedBatchId>
      </payment>
    </payments>
  </OrderUpdate>
</OrderUpdates>
```
