---
slug: exporting-sales-orders-from-sage-50-us
title: Exporting Sales Orders from Sage 50 US
---
This task will export sales order information from Sage 50 US in the [Sage 50 US Sales Order XML](sage-50-us-sales-order-xml) format. You can choose to export either all, modified or only new records, and can filter the exports if only a subset of your sales order records are required.

## Settings
### Sage Connection
_Required_  
The connection to Sage 50 US to use. See the [Connecting to Sage 50 US](connecting-to-sage-50-us) article if you require more information on how to create/manage connections.

### Export New, Modified or All Records
_Required_  
Setting to determine which records are exported from Sage. New will only export records created since the last time Zynk was ran. Modified will only export records updated in Sage since the last time Zynk was ran. All will always export all records.

### Filters
_Optional_  
Settings to allow only specific records to be exported from Sage. See the [Sage 50 US Filters](sage-50-us-filters) article for more information.

### Output File
_Required_  
The name of the file to export to. Data is exported in [Sage 50 US Sales Order XML](sage-50-us-sales-order-xml) format.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage 50 US Sales Order XML](sage-50-us-sales-order-xml) for full documentation of the XML format.
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