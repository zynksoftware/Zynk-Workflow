---
slug: importing-purchase-orders-into-sage-50-us
title: Importing Purchase Orders into Sage 50 US
---
This task will import purchase order information in the [Sage 50 US Purchase Order XML](sage-50-us-purchase-order-xml) format into Sage 50 US.

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
Set this to 'True' to check whether the supplied purchase order Id has already been imported, and if so skip the purchase order. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage 50 US Purchase Order XML](sage-50-us-purchase-order-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder>
  <PurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>2317</ExternalId>
    <Key>2ff80f5a-d4c2-4e9c-9151-4ca9e3fa87de</Key>
    <ReferenceNumber />
    <Date>2015-03-15T00:00:00</Date>
    <Amount>215.8500000000000000000</Amount>
    <LastSavedAt>0001-01-01T00:00:00</LastSavedAt>
    <IsPosted>true</IsPosted>
    <AccountReference>20000-00</AccountReference>
    <ShipToAddress>
      <Name>Bellwether Garden Supply</Name>
      <Address>
        <Address1>1505 Pavilion Place</Address1>
        <Address2 />
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30093-3203</Zip>
        <Country>USA</Country>
        <SalesTaxCode />
      </Address>
    </ShipToAddress>
    <ShipVia>None</ShipVia>
    <TermsDescription>2% 10, Net 30 Days</TermsDescription>
    <InternalNote />
    <DiscountAmount>4.3200000000000000000</DiscountAmount>
    <VendorReference>SOGARDEN</VendorReference>
    <PrintVendorNoteAfterLineItems>false</PrintVendorNoteAfterLineItems>
    <VendorNote />
    <MainAddress>
      <Name>Southern Garden Wholesale</Name>
      <Address>
        <Address1>4555 Oakland Park Blvd.</Address1>
        <Address2 />
        <City>Atlanta</City>
        <State>GA</State>
        <Zip>30312</Zip>
        <Country>USA</Country>
        <SalesTaxCode />
      </Address>
    </MainAddress>
    <GoodThroughDate>2015-04-14T00:00:00</GoodThroughDate>
    <IsClosed>false</IsClosed>
    <IsDropShip>false</IsDropShip>
    <DiscountDate xsi:nil="true" />
    <PurchaseOrderLines>
      <PurchaseOrderLine>
        <AccountReference>12000-00</AccountReference>
        <Amount>215.8500000000000000000</Amount>
        <Description>Catalog # LM400500 Rotary Lawn Mower - 3HP</Description>
        <IsUsed>true</IsUsed>
        <InventoryItemReference>EQLW-14130</InventoryItemReference>
        <Quantity>3.0000000000000000000</Quantity>
        <UnitPrice>71.9500000000000000000</UnitPrice>
        <QuantityReceived>0.0000000000000000000</QuantityReceived>
      </PurchaseOrderLine>
    </PurchaseOrderLines>
  </PurchaseOrder>
</ArrayOfPurchaseOrder>
```