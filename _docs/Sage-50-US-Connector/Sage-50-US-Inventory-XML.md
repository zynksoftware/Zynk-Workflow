---
slug: sage-50-us-inventory-xml
title: Sage 50 US Inventory XML
---
Export Inventory allows you to export All, Modified and New inventory records from Sage 50 US. As its possible to change the Id of inventory items in Sage we would recommend to store the Key field in third party systems as well as the Id so these changes can be handled.  

Any Sage fields not documented below are not supported with our exports, if there are additional fields you need contact us at support@zynk.com.  

## Current limitations 
 * Quantity fields - we can only get access to the Qty on Hand field, so you will always get the full stock value.  If any stock is allocated against sales orders these quantities will not be taken into account.
 * Pricing - we export the sale price from Price Level 1.  If the price level is based on a calculation e.g. cost price you will need to manually recalc pricing in the Sage program for us to export the new prices. 

Sample file for the various inventory types:-

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>656c5b6b-b372-4bd8-ac37-70922f3eb9c9</Key>
    <Id>FRIEGHT-EQ</Id>
    <PartNumber />
    <Type>NonStockItem</Type>
    <Description>Freight on equipment</Description>
    <Category />
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>0.00</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    </CustomFields>
    <DescriptionForSales />
    <DescriptionForPurchases />
    <BuyerReference />
    <COGSAccountReference>50000-EQ</COGSAccountReference>
    <Location />
    <SalaryAccountReference>57500-EQ</SalaryAccountReference>
    <SalesAccountReference>40000-EQ</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
    <VendorReference />
    <Weight>0.00</Weight>
  </Inventory>
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
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>77b5a228-d976-4d9b-96ad-62fffa5fa06e</Key>
    <Id>TOOL-35600</Id>
    <PartNumber />
    <Type>AssemblyItem</Type>
    <Description>Garden Hoe Kit</Description>
    <Category>SUPPLY</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>39.99</SalePrice>
    <QtyOnHand>6.00</QtyOnHand>
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
    <DescriptionForSales>Garden Hoe Kit</DescriptionForSales>
    <DescriptionForPurchases>Catalog #S100425: Grass Shears</DescriptionForPurchases>
    <BuyerReference />
    <COGSAccountReference>50000-HT</COGSAccountReference>
    <Location>AISLE 5</Location>
    <SalesAccountReference>40000-HT</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
    <VendorReference>DEJULIA</VendorReference>
    <Weight>0.00</Weight>
    <CostingMethod>FIFO</CostingMethod>
    <InventoryAccountReference>12000-00</InventoryAccountReference>
    <MinimumStock>3.00</MinimumStock>
    <ReorderQuantity>6.00</ReorderQuantity>
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>6ead2e83-e48d-4799-b4ee-b7305bff2017</Key>
    <Id>LAND-17100</Id>
    <PartNumber />
    <Type>ServiceItem</Type>
    <Description>Landscaping Service - Weekly</Description>
    <Category>SERVICE</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>false</IsTaxable>
    <SalesTaxType>2</SalesTaxType>
    <SalePrice>49.99</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    <DescriptionForSales>Weekly Landscaping Service</DescriptionForSales>
    <DescriptionForPurchases />
    <COGSAccountReference>57000-LS</COGSAccountReference>
    <Location />
    <SalaryAccountReference>77500-00</SalaryAccountReference>
    <SalesAccountReference>40000-LS</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
    <VendorReference />
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>a78f63d8-6dff-4b93-bd1e-361cfd650793</Key>
    <Id>NURS-21100</Id>
    <PartNumber />
    <Type>LaborItem</Type>
    <Description>Nursery Labor</Description>
    <Category>LABOR</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>39.99</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    <DescriptionForSales>Nursery Prep and Labor</DescriptionForSales>
    <DescriptionForPurchases />
    <COGSAccountReference>57000-NU</COGSAccountReference>
    <Location />
    <SalaryAccountReference>77500-00</SalaryAccountReference>
    <SalesAccountReference>40000-NU</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
    <VendorReference />
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>684a25e8-391e-47e6-8548-aeff0e737375</Key>
    <Id>B&amp;W COPY</Id>
    <PartNumber />
    <Type>ChargeItem</Type>
    <Description>B&amp;W Plan Copy</Description>
    <Category />
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>25.00</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    <DescriptionForSales>Black and white copy of Scale Plan</DescriptionForSales>
    <Location />
    <SalesAccountReference>40000-MI</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>22e93413-1a84-4837-b9cf-bcbfbf5e4f81</Key>
    <Id>ADMIN-01000</Id>
    <PartNumber />
    <Type>ActivityItem</Type>
    <Description>Bookkeeping/Administrative</Description>
    <Category>ADMIN</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>false</IsTaxable>
    <SalesTaxType>2</SalesTaxType>
    <SalePrice>0.00</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    <DescriptionForSales>(Internal) Bookkeeping and Administrative Duties for Front Office</DescriptionForSales>
    <Location />
    <SalesAccountReference>40000-00</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>cde56043-fbbc-4086-9421-361a7756613c</Key>
    <Id>AVRY-10050</Id>
    <PartNumber />
    <Type>MasterStockItem</Type>
    <Description>Prefabricated Birdhouse</Description>
    <Category>SUPPLY</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>59.99</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    <DescriptionForSales>Prefabricated Birdhouse</DescriptionForSales>
    <DescriptionForPurchases />
    <BuyerReference>MTROTTER</BuyerReference>
    <COGSAccountReference>50000-00</COGSAccountReference>
    <Location>Row 9</Location>
    <SalesAccountReference>40000-AV</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <VendorReference>ABNEY</VendorReference>
    <Weight>1.60</Weight>
    <CostingMethod>FIFO</CostingMethod>
    <InventoryAccountReference>12000-00</InventoryAccountReference>
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>156707c3-b236-4584-9bb7-37f3a558466d</Key>
    <Id>AVRY-10050-LG-CSL</Id>
    <PartNumber>15675</PartNumber>
    <Type>SubStockItem</Type>
    <Description>Prefabricated Birdhouse</Description>
    <Category>SUPPLY</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>79.99</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    <DescriptionForSales>Prefabricated Birdhouse-Large Castle</DescriptionForSales>
    <DescriptionForPurchases />
    <BuyerReference>MTROTTER</BuyerReference>
    <COGSAccountReference>50000-00</COGSAccountReference>
    <Location>Row 9</Location>
    <SalesAccountReference>40000-AV</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC>2323460</UPC>
    <VendorReference>ABNEY</VendorReference>
    <Weight>2.30</Weight>
    <CostingMethod>FIFO</CostingMethod>
    <InventoryAccountReference>12000-00</InventoryAccountReference>
    <MinimumStock>10.00</MinimumStock>
    <ReorderQuantity>15.00</ReorderQuantity>
    <MasterItemID>AVRY-10050</MasterItemID>
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>6ccaec2e-59ed-46e2-ab39-62aff21f997e</Key>
    <Id>EQLW-14200</Id>
    <PartNumber />
    <Type>SerializedStockItem</Type>
    <Description>Riding Mower-14 HP</Description>
    <Category>SUPPLY</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>2899.00</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    <DescriptionForSales>Riding Lawn Mower - 14 Horse Power</DescriptionForSales>
    <DescriptionForPurchases />
    <BuyerReference>VANSELL</BuyerReference>
    <COGSAccountReference>50000-EQ</COGSAccountReference>
    <Location>AISLE 4</Location>
    <SalesAccountReference>40000-EQ</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
    <VendorReference>SOGARDEN</VendorReference>
    <Weight>0.00</Weight>
    <CostingMethod>SpecificUnit</CostingMethod>
    <InventoryAccountReference>12000-00</InventoryAccountReference>
    <MinimumStock>5.00</MinimumStock>
    <ReorderQuantity>2.00</ReorderQuantity>
  </Inventory>
  <Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Key>8a74d71d-4af7-45c4-9f17-9be239b2b34f</Key>
    <Id>MOWER-184W</Id>
    <PartNumber />
    <Type>SerializedAssemblyItem</Type>
    <Description>18" Reel Mower with Tracking</Description>
    <Category>MANF</Category>
    <Note />
    <IsInactive>false</IsInactive>
    <IsTaxable>true</IsTaxable>
    <SalesTaxType>1</SalesTaxType>
    <SalePrice>239.99</SalePrice>
    <QtyOnHand>0</QtyOnHand>
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
    </CustomFields>
    <DescriptionForSales>Classic 18" reel mower with fingertip height control. Dual wheel tracking handles rough terrain.</DescriptionForSales>
    <DescriptionForPurchases />
    <BuyerReference />
    <COGSAccountReference>50000-MF</COGSAccountReference>
    <Location>F200</Location>
    <SalesAccountReference>40000-MF</SalesAccountReference>
    <SubjectToCommission>false</SubjectToCommission>
    <UPC />
    <VendorReference />
    <Weight>0.00</Weight>
    <CostingMethod>SpecificUnit</CostingMethod>
    <InventoryAccountReference>12150-00</InventoryAccountReference>
    <MinimumStock>10.00</MinimumStock>
    <ReorderQuantity>5.00</ReorderQuantity>
  </Inventory>
</ArrayOfInventory>
```