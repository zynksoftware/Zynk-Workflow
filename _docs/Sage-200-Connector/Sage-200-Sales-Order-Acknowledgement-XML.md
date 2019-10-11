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
| UniqueId | - | 2841241 | int | - | Optional | The database ID of the sales order. In the Zynk SalesOrder object, this would be the UniqueId specified in the success file of a successfully imported SalesOrder or in the export file from Sage 200. If this data is obtained directly from the Sage database, then this relates to SOPOrderReturn.SOPOrderReturnID |
| SalesOrderNumber | Order no | 0000000005 | string | 10 | Optional | The Order no of the sales order. In the Zynk SalesOrder object, this would be the SaleseOrderNumber specified in the success file of a successfully imported SalesOrder or in the export file from Sage 200. If this data is obtained directly from the Sage database, then this relates to  SOPOrderReturn.DocumentNo |
| Id | - | 12345 | string | 255 | Optional | The Id of the Zynk SalesOrder. If the SalesOrder was previously imported by Zynk and an Id (3rd party system identifier) was specified in the XML, then this can be used to match the sales order. This will only be valid in scenarios where the SalesOrder was created by Zynk and an Id was specified. This is not something that can be obtained directly from the Sage 200 database. |
| CustomerOrderNumber | Customer order no | ABC12345 | string | 30 | Optional | The Customer order no of the sales order. In the Zynk SalesOrder object, this would be the CustomerOrderNumber specified in the success file of a successfully imported SalesOrder or in the export file from Sage 200. If this data is obtained directly from the Sage database, then this relates to SOPOrderReturn.CustomerDocumentNo |

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
