---
slug: importing-sales-orders-into-sage-50-us
redirect_from: "/article/387-importing-sales-orders-into-sage-50-us"
title: Importing Sales Orders into Sage 50 US
---
This task will import sales order information in the [Sage 50 US Sales Order XML](sage-50-us-sales-order-xml) format into Sage 50 US.

## Settings
### Sage Connection
_Required_  
The connection to Sage 50 US to use. See the [Connecting to Sage 50 US](connecting-to-sage-50-us) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file that you want to import in XML format.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.

### Prevent Duplicates
_Required_  
Set this to 'True' to check whether the supplied sales order Id has already been imported, and if so skip the sales order. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage 50 US Sales Order XML](sage-50-us-sales-order-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfSalesOrder>
  <SalesOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>123</ExternalId>
    <CustomerReference>ARMSTRONG</CustomerReference>
    <ShipToAddress>
      <Name>Harding Consulting</Name>
      <Address>
        <Address1>2300 Club Drive</Address1>
        <Address2>Suite A</Address2>
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30093</Zip>
        <Country />
      </Address>
    </ShipToAddress>
    <Date>2015-03-02T00:00:00</Date>
    <ShipByDate>2015-03-02T00:00:00</ShipByDate>
    <ReferenceNumber>10322</ReferenceNumber>
    <IsDropShip>false</IsDropShip>
    <CustomerPurchaseOrderNumber />
    <ShipVia>None</ShipVia>
    <AccountReference>11000-00</AccountReference>
    <SalesTaxCodeReference>GAGWINN</SalesTaxCodeReference>
    <FreightAmount>0</FreightAmount>
    <FreightAccountReference>57500-00</FreightAccountReference>
    <CustomerNote />
    <PrintCustomerNoteAfterLineItems>false</PrintCustomerNoteAfterLineItems>
    <StatementNote>Thank you for choosing Bellwether Garden Supply!</StatementNote>
    <InternalNote />
    <SalesOrderLines>
      <SalesOrderLine>
        <Quantity>2.00</Quantity>
        <InventoryItemReference>BOOK-11010</InventoryItemReference>
        <Description>Bell-Grow Series: Gardening Handbook (Madison)</Description>
        <AccountReference>40000-BK</AccountReference>
        <UnitPrice>29.95</UnitPrice>
        <SalesTaxType>1</SalesTaxType>
  <JobReference>SHARP</JobReference>  
      </SalesOrderLine>
    </SalesOrderLines>
  </SalesOrder>
</ArrayOfSalesOrder>
```