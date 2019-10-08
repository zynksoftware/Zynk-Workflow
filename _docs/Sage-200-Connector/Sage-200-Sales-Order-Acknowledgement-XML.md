---
slug: sage-200-sales-order-acknowledgement-xml
title: Sage 200 Sales Order Acknowledgement XML
---
The [Import Sales Order Acknowledgements into Sage 200](importing-sales-order-acknowledgements-into-sage-200) task allows you to acknowledge existing orders in Sage 200. The only information that needs to be provided in the XML is a list of orders you would like to acknowledge.

Please note that only orders of the type 'Sales Order' can be acknowledged.

## Order Identification
At least one of the following fields must be provided to identify which order to acknowledge in Sage. The fields will be considered in the following order: UniqueId, SalesOrderNumber, Id, CustomerOrderNumber. If no match is found based on any of these fields, the order won't be acknowledged.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| UniqueId | - | 2841241 | int | - | Optional | Used to specify the SOPOrderReturn.SOPOrderReturnID value from the Sage database. |
| SalesOrderNumber | Order no | 0000000005 | string | 10 | Optional | |
| Id | - | 12345 | string | 255 | Optional | Only works where an order was imported into Sage via Zynk, and an Id was specifed at the time. |
| CustomerOrderNumber | Customer order no | ABC12345 | string | 30 | Optional | |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <SalesOrders>
    <SalesOrder>
      <UniqueId>2841241</UniqueId>
      <SalesOrderNumber>0000000005</SalesOrderNumber>
      <Id>12345</Id>
      <CustomerOrderNumber>ABC12345</CustomerOrderNumber>
    </SalesOrder>
  </SalesOrders>
</Company>
```