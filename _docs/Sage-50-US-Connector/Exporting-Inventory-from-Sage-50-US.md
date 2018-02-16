---
slug: exporting-inventory-from-sage-50-us
redirect_from: "/article/386-exporting-inventory-from-sage-50-us"
title: Exporting Inventory from Sage 50 US
---
This task will export inventory information from Sage 50 US in the [Sage 50 US Inventory XML](sage-50-us-inventory-xml) format. You can choose to export either all, modified or only new records, and can filter the exports if only a subset of your inventory records are required.

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
The name of the file to export to. Data is exported in [Sage 50 US Inventory XML](sage-50-us-inventory-xml) format.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage 50 US Inventory XML](sage-50-us-inventory-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>9683178a-43f4-4c47-b27f-e6e9f45dc8c3</Key>
    <Id>AVRY-10110</Id>
    <PartNumber />
    <Type>StockItem</Type>
    <Description>Bird House-Pole 14 Ft.</Description>
    <Category>SUPPLY</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>49.99</SalePrice>
    <QtyOnHand>58.00</QtyOnHand>
    <CustomFields>
      <CustomField>
        <Name>Alternate Vendor</Name>
        <Value />
      </CustomField>
      <CustomField>
        <Name>Substitution</Name>
        <Value />
      </CustomField>
      <CustomField>
        <Name>Special Note</Name>
        <Value />
      </CustomField>
      <CustomField>
        <Name>Special Order</Name>
        <Value />
      </CustomField>
    </CustomFields>
    <DescriptionForSales>Three-Section pole that will place the bird house 12 ft. above ground</DescriptionForSales>
    <DescriptionForPurchases>Catalog #B11225: Bird House-Pole 14 Ft.</DescriptionForPurchases>
    <BuyerReference />
    <COGSAccountReference>50000-AV</COGSAccountReference>
    <Location>AISLE 1</Location>
    <SalesAccountReference>40000-AV</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
    <VendorReference>DEJULIA</VendorReference>
    <Weight>0.00</Weight>
    <CostingMethod>FIFO</CostingMethod>
    <InventoryAccountReference>12000-00</InventoryAccountReference>
    <MinimumStock>6.00</MinimumStock>
    <ReorderQuantity>6.00</ReorderQuantity>
  </Inventory>
</ArrayOfInventory>
```