---
slug: exporting-orders-from-shipstation
title: Exporting Orders from ShipStation
---
This task will export orders from ShipStation in XML format.

## Settings
### ShipStation Connection
_Required_  
Select a ShipStation connection to use. See the [Connecting to ShipStation](connecting-to-shipstation) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Created** - Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.

### Order Status
_Optional_  
Select an order status from the list if you want to only export orders that are at a particular status, or leave blank to export orders at any status. The following options are available:

 * awaiting_payment
 * awaiting_shipment
 * shipped
 * on_hold
 * cancelled

### Output File
_Required_  
The name of the file to export the orders to. Data is exported in XML format, as shown below.

### Page Size
_Required_  
The number of records to fetch per page. Defaults to 100, maximum 500.

### Store ID
_Required_  
Select an store from the list if you want to only export orders from a particular store, or leave blank to export orders from all stores.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <Id>408458053</Id>
    <OrderNumber>984543</OrderNumber>
    <OrderKey>319072f1-0a58-4f94-9425-c5876e7082f1</OrderKey>
    <OrderDate>2019-07-29T00:00:00</OrderDate>
    <CreateDate>2019-07-29T07:35:56.09</CreateDate>
    <ModifyDate>2019-07-29T08:22:24.547</ModifyDate>
    <PaymentDate xsi:nil="true" />
    <ShipByDate xsi:nil="true" />
    <OrderStatus>awaiting_shipment</OrderStatus>
    <CustomerId xsi:nil="true" />
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
      <Phone />
      <Residential>false</Residential>
      <AddressVerified>Address validated successfully</AddressVerified>
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
      <Phone />
      <Residential>false</Residential>
      <AddressVerified>Address validated successfully</AddressVerified>
    </ShipTo>
    <Items>
      <OrderItem>
        <Id>40548608</Id>
        <OrderItemId>556733634</OrderItemId>
        <LineItemKey>0</LineItemKey>
        <Sku>SAGE50</Sku>
        <Name>Sage 50 Pro</Name>
        <Quantity>1</Quantity>
        <UnitPrice>200.00</UnitPrice>
        <TaxAmount>40.00</TaxAmount>
        <ShippingAmount xsi:nil="true" />
        <Options />
        <Adjustment>false</Adjustment>
        <CreateDate>2019-07-29T07:35:56.09</CreateDate>
        <ModifyDate>2019-07-29T07:35:56.09</ModifyDate>
      </OrderItem>
    </Items>
    <OrderTotal>240.00</OrderTotal>
    <AmountPaid>0.00</AmountPaid>
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
    <ExternallyFulfilled>false</ExternallyFulfilled>
  </Order>
</Orders>
```
