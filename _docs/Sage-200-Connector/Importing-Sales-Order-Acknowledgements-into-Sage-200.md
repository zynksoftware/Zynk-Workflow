---
slug: importing-sales-order-acknowledgements-into-sage-200
title: Importing Sales Order Acknowledgements into Sage 200
---
This task will acknowledge existing Sales Orders in Sage 200, based on an XML file formatted in Zynk XML format.

## Settings
### Connection Settings
#### Sage 200 Connection
_Required_  
The Sage 200 connection to use. See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### File Settings
#### Fail File
_Required_  
The name of the file to output any failed sales order acknowledgements to. The data will be outputted in Zynk XML format.

#### Input File
_Required_  
The source file for containing the sales orders to acknowledge. The file must be in Zynk XML format, as shown in the example below.

#### Success File
_Required_  
The name of the file to output successful sales order acknowledgements to. The data will be outputted in Zynk XML format.

## Examples
A sample input file for acknowledging a sales order is shown below. See [Sage 200 Sales Order Acknowledgement XML](sage-200-sales-order-acknowledgement-xml) for more details on the Zynk XML Sales Order format for Sage 200.

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
