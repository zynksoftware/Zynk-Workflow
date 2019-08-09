---
slug: marking-orders-as-shipped-in-shipstation
title: Marking Orders as Shipped in ShipStation
---
This task will import mark existing orders as shipped in ShipStations, without creating a shipping label. The orders to ship must be supplied in XML format.

## Settings
### ShipStation Connection
_Required_  
Select a ShipStation connection to use. See the [Connecting to ShipStation](connecting-to-shipstation) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file containing the orders to mark as shipped into ShipStation. The file must contain XML data, in the format shown below.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Prevent Duplicates
_Required_  
Set this to 'True' to check whether the ExternalId of each order supplied in the input XML file has already been imported, and if so skip the record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [ShipStation Mark Orders as Shipped XML](shipstation-mark-orders-as-shipped-xml):  

```xml
<?xml version="1.0" encoding="utf-8"?>
<ShipOrders>
  <ShipOrder>
    <ExternalId>64362</ExternalId>
    <OrderNumber>123456</OrderNumber>
    <OrderId>3151356</OrderId>
    <CarrierCode>dpd</CarrierCode>
    <ShipDate>2019-08-01</ShipDate>
    <TrackingNumber>12038172084</TrackingNumber>
    <NotifyCustomer>false</NotifyCustomer>
    <NotifySalesChannel>false</NotifySalesChannel>
  </ShipOrder>
</ShipOrders>
```