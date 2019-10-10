---
slug: sage-200-convert-proformas-to-sales-orders-xml
title: Sage 200 Convert Proformas To Sales Orders XML
---
The [Convert Proformas to Sales Orders](converting-proformas-to-sales-orders) task allows you to convert existing proformas in Sage 200 to sales orders. The only information that needs to be provided in the XML is a list of the proformas you would like to convert.

Please note that only orders of the type 'Proforma' can be converted.

## Proforma Identification
At least one of the following fields must be provided to identify which proforma to convert in Sage. The fields will be considered in the following order: UniqueId, SalesOrderNumber, Id, CustomerOrderNumber. If no match is found based on any of these fields, the proforma won't be converted.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| UniqueId | - | 2841241 | int | - | Optional | Used to specify the SOPOrderReturn.SOPOrderReturnID value from the Sage database. |
| SalesOrderNumber | Order no | 0000000005 | string | 10 | Optional | |
| Id | - | 12345 | string | 255 | Optional | Only works where a proforma was imported into Sage via Zynk, and an Id was specified at the time. |
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