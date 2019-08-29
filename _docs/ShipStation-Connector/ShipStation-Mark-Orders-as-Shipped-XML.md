---
slug: shipstation-mark-orders-as-shipped-xml
title: ShipStation Mark Orders As Shipped XML
---
The [Mark Orders as Shipped](marking-orders-as-shipped-in-shipstation) task allows you to mark orders as shipped in ShipStation, without creating a shipping label. Any fields not documented below are not supported by our import.

Sample import file showing the minimum info required to mark an order as shipped:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ShipOrders>
  <ShipOrder>
    <OrderId>3151356</OrderId>
    <CarrierCode>dpd</CarrierCode>
  </ShipOrder>
</ShipOrders>
```

## Fields  
The following info can be specified in the Ship Order XML.

| ShipStation Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- | --- |
| - | ExternalId* | 64362 | string | Optional |
| - | OrderId* | 2415 | int | Dependant |
| Order# | OrderNumber* | 123456 | string | Dependant |
| Carrier | CarrierCode | dpd | string | Required |
| Ship Date | ShipDate | 2019-01-01 | date | Optional |
| Tracking# | TrackingNumber | 12038172084 | string | Optional |
| Notify Customer? | NotifyCustomer | false | bool | Optional |
| Notify Marketplace? | NotifySalesChannel | false | bool | Optional |

*   ExternalId* - Used internally by Zynk to track which orders have been processed. Must be provided for the 'Prevent Reprocessing' task setting to work.
*   OrderId* - Either the OrderId or OrderNumber must be specified. If both are specified, OrderId takes precenence.
*   OrderNumber* - Either the OrderId or OrderNumber must be specified. If both are specified, OrderId takes precenence.

```xml
<?xml version="1.0" encoding="utf-8"?>
<ShipOrders>
  <ShipOrder>
    <ExternalId>64362</ExternalId>
    <OrderId>2415</OrderId>
    <OrderNumber>123456</OrderNumber>
    <CarrierCode>dpd</CarrierCode>
    <ShipDate>2019-01-01</ShipDate>
    <TrackingNumber>12038172084</TrackingNumber>
    <NotifyCustomer>false</NotifyCustomer>
    <NotifySalesChannel>false</NotifySalesChannel>
  </ShipOrder>
</ShipOrders>
```
