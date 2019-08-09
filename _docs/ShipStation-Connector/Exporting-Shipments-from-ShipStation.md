---
slug: exporting-shipments-from-shipstation
title: Exporting Shipments from ShipStation
---
This task will export shipments from ShipStation in XML format. Please note that it will not export orders that have been marked as shipped, as no shipment is generated in ShipStation for these orders.

## Settings
### ShipStation Connection
_Required_  
Select a ShipStation connection to use. See the [Connecting to ShipStation](connecting-to-shipstation) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Created** - Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export.

### Order Numbers
_Optional_  
Enter a comma separated list of order numbers to export shipments for specific orders. If you use this setting, it will override the options specified in Export Settings.

### Output File
_Required_  
The name of the file to export the shipments to. Data is exported in XML format, as shown below.

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
<Shipments xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Shipment>
    <Id>187978118</Id>
    <OrderId>336564688</OrderId>
    <OrderKey>6ba19052-7013-4e9f-bdc7-f7f427e02232</OrderKey>
    <UserId>6a01d6e8-c15a-4d24-83c0-330b5acf6076</UserId>
    <OrderNumber>984528</OrderNumber>
    <CreateDate>2019-02-26T06:57:33.427</CreateDate>
    <ShipDate>2019-02-27T00:00:00</ShipDate>
    <ShipmentCost>27.72</ShipmentCost>
    <InsuranceCost>124.20</InsuranceCost>
    <TrackingNumber>5984059944</TrackingNumber>
    <IsReturnLabel>false</IsReturnLabel>
    <CarrierCode>dhl_express_uk</CarrierCode>
    <ServiceCode>dhl_uk_domestic_express</ServiceCode>
    <PackageCode>package</PackageCode>
    <WarehouseId>610360</WarehouseId>
    <Voided>false</Voided>
    <VoidDate xsi:nil="true" />
    <MarketplaceNotified>true</MarketplaceNotified>
    <ShipTo>
      <Name>John Smith</Name>
      <Company>Zynk Software Limited</Company>
      <Street1>8 Newcastle Enterprise Centres</Street1>
      <Street2>6 Charlotte Square</Street2>
      <City>Newcastle Upon Tyne</City>
      <State>Tyne and Wear</State>
      <PostalCode>NE1 4XF</PostalCode>
      <Country>GB</Country>
      <Phone>0191 303 7279</Phone>
      <Residential xsi:nil="true" />
    </ShipTo>
    <Weight>
      <Value>10.00</Value>
      <Units>grams</Units>
    </Weight>
    <Dimensions>
      <Units>inches</Units>
      <Length>1.00</Length>
      <Width>3.00</Width>
      <Height>4.00</Height>
    </Dimensions>
    <InsuranceOptions>
      <InsureShipment>false</InsureShipment>
      <InsuredValue>0.0</InsuredValue>
    </InsuranceOptions>
    <AdvancedOptions>
      <WarehouseId xsi:nil="true" />
      <NonMachinable xsi:nil="true" />
      <SaturdayDelivery xsi:nil="true" />
      <ContainsAlcohol xsi:nil="true" />
      <MergedOrSplit xsi:nil="true" />
      <MergedIds />
      <ParentId xsi:nil="true" />
      <StoreId>227725</StoreId>
    </AdvancedOptions>
    <ShipmentItems>
      <ShipmentItem>
        <OrderItemId>457619610</OrderItemId>
        <LineItemKey>0</LineItemKey>
        <Sku>SHIP1001</Sku>
        <Name>Shipstation</Name>
        <Weight xsi:nil="true" />
        <Quantity>1</Quantity>
        <UnitPrice>6900.00</UnitPrice>
        <ProductId>40548160</ProductId>
      </ShipmentItem>
    </ShipmentItems>
  </Shipment>
</Shipments>
```
