---
slug: importing-orders-into-shipstation
title: Importing Orders into ShipStation
---
This task will import orders into ShipStations, that are supplied in XML format.

## Settings
### ShipStation Connection
_Required_  
Select a ShipStation connection to use. See the [Connecting to ShipStation](connecting-to-shipstation) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file containing the orders to import into ShipStation. The file must contain XML data, in the format shown below.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Prevent Duplicates
_Required_  
Set this to 'True' to check whether the ExternalId of each order supplied in the input XML file has already been imported, and if so skip the record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [ShipStation Order XML](shipstation-order-xml):  

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <ExternalId>984543</ExternalId>
    <OrderNumber>984543</OrderNumber>
    <OrderKey>319072f1-0a58-4f94-9425-c5876e7082f1</OrderKey>
    <OrderDate>2019-07-29T00:00:00</OrderDate>
    <PaymentDate>2019-07-29T00:00:00</PaymentDate>
    <ShipByDate>2019-07-30T00:00:00</ShipByDate>
    <OrderStatus>awaiting_shipment</OrderStatus>
    <CustomerUsername>zynksoftware</CustomerUsername>
    <CustomerEmail>support@zynk.com</CustomerEmail>
    <BillTo>
      <Name>John Smith</Name>
      <Company>Zynk Software Limited</Company>
      <Street1>8 Newcastle Enterprise Centres</Street1>
      <Street2>6 Charlotte Square</Street2>
      <Street3 />
      <City>Newcastle Upon Tyne</City>
      <State>Tyne and Wear</State>
      <PostalCode>NE1 4XF</PostalCode>
      <Country>GB</Country>
      <Phone>0191 303 7279</Phone>
      <Residential>false</Residential>
    </BillTo>
    <ShipTo>
      <Name>John Smith</Name>
      <Company>Zynk Software Limited</Company>
      <Street1>8 Newcastle Enterprise Centres</Street1>
      <Street2>6 Charlotte Square</Street2>
      <Street3 />
      <City>Newcastle Upon Tyne</City>
      <State>Tyne and Wear</State>
      <PostalCode>NE1 4XF</PostalCode>
      <Country>GB</Country>
      <Phone>0191 303 7279</Phone>
      <Residential>false</Residential>
    </ShipTo>
    <Items>
      <OrderItem>
        <LineItemKey>0</LineItemKey>
        <Sku>SAGE50</Sku>
        <Name>Sage 50 Pro</Name>
        <Quantity>1</Quantity>
        <UnitPrice>200.00</UnitPrice>
        <TaxAmount>40.00</TaxAmount>
        <ShippingAmount xsi:nil="true" />
        <Options />
        <Adjustment>false</Adjustment>
      </OrderItem>
    </Items>
    <AmountPaid>240.00</AmountPaid>
    <TaxAmount>40.00</TaxAmount>
    <ShippingAmount>0.00</ShippingAmount>
    <Gift>false</Gift>
    <CarrierCode>hermes</CarrierCode>
    <ServiceCode>hermes_domestic_parcelshop_dropoff</ServiceCode>
    <PackageCode>package</PackageCode>
    <Confirmation>none</Confirmation>
    <ShipDate xsi:nil="true" />
    <HoldUntilDate xsi:nil="true" />
    <Weight>
      <Value>0.28</Value>
      <Units>ounces</Units>
    </Weight>
    <Dimensions>
      <Units>inches</Units>
      <Length>2.00</Length>
      <Width>3.00</Width>
      <Height>1.00</Height>
    </Dimensions>
    <InsuranceOptions>
      <InsureShipment>false</InsureShipment>
      <InsuredValue>0.0</InsuredValue>
    </InsuranceOptions>
    <InternationalOptions>
      <Contents xsi:nil="true" />
      <NonDelivery xsi:nil="true" />
    </InternationalOptions>
    <AdvancedOptions>
      <WarehouseId>610360</WarehouseId>
      <NonMachinable>false</NonMachinable>
      <SaturdayDelivery>false</SaturdayDelivery>
      <ContainsAlcohol>false</ContainsAlcohol>
      <MergedOrSplit>false</MergedOrSplit>
      <MergedIds />
      <ParentId xsi:nil="true" />
      <StoreId>227725</StoreId>
    </AdvancedOptions>
  </Order>
</Orders>
```