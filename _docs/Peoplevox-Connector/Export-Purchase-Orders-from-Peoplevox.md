---
slug: export-purchase-orders-from-peoplevox
title: Export Purchase Orders from Peoplevox
---

This task will export purchase order information from Peoplevox in XML format, for detailed information see [Peoplevox Purchase Order XML](peoplevox-purchase-order-xml).  The information is exported using the "Purchase orders" integration template as setup through your Peoplevox web application.  You can add search clauses to limit the data that is returned.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### API Call Delay
_Required_  
The number of seconds to wait between sending requests to the Peoplevox API, used when making multiple paged requests to export data.  Defaults to 1.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_item_types.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example input file, for detailed information see [Peoplevox Purchase Order XML](peoplevox-purchase-order-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<PurchaseOrders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrder>
  <PurchaseOrder>
    <PurchaseOrderNumber>199</PurchaseOrderNumber>
    <Status>Submitted</Status>
    <Reference>199</Reference>
    <Supplier>Test Supplier</Supplier>
    <AddressLine1>i6 Business Centre</AddressLine1>
    <AddressLine2>Charlotte Square</AddressLine2>
    <AddressCity>Newcastle</AddressCity>
    <AddressRegion>Tyne and Wear</AddressRegion>
    <AddressPostcode>NE1 4XF</AddressPostcode>
    <AddressCountry>United Kingdom</AddressCountry>
    <AddressReference />
    <RequestedDeliveryDate>04/07/2017 23:00:00</RequestedDeliveryDate>
    <SubmittedDate>05/07/2017 10:37:06</SubmittedDate>
    <User>Admin</User>
    <EndDate />
    <ExpectedDeliveryDate>04/07/2017 23:00:00</ExpectedDeliveryDate>
    <PurchaseOrderItems>
      <PurchaseOrderItem>
        <PurchaseOrderNumber>199</PurchaseOrderNumber>
        <ItemCode>TEST01</ItemCode>
        <Status>Pending</Status>
        <Quantity>1</Quantity>
        <RequestedDeliveryDate />
        <Line>TEST01</Line>
        <Sequence>1</Sequence>
        <CostPrice>1.00</CostPrice>
      </PurchaseOrderItem>
    </PurchaseOrderItems>
  </PurchaseOrder>
</PurchaseOrders>
```