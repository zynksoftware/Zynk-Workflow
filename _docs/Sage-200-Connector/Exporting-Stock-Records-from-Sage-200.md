---
slug: exporting-stock-records-from-sage-200
redirect_from: "/article/433-exporting-stock-records-from-sage-200"
title: Exporting Stock Records from Sage 200
---
This task will export new, modified or all stock records in [Sage 200 XML](sage-200-xml) format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Characters To Cleanse
_Optional_  
A list of characters to remove from the output file. Use this if your Sage data contains characters that are not valid for XML documents (e.g. 	`&#x0;`).

### Export BOMs
_Required_  
Set to true to export the bill of materials for each product. Defaults to false.

### Export Locations
_Required_  
Set to true to export detailed location information for each product. Defaults to false

### Export Settings
_Optional_  

 * **Date Created** - Used when exporting new records. Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.
 * **Op Lock** - Used when exporting modified records. Only records where the Op Lock is greater than this value will be exported. The value will update automatically each time the task runs.

### Export Traceable Items
_Required_  
Set to true to export detailed batch/serial number information for each product. Export Locations must be set to true for this setting to take effect. Defaults to false.

### Query Settings
_Optional_  

 * **Columns** - Used to enter the column names to export from the Sage database. Be sure to include the table name eg. `[SLCustomerAccount].[CustomerAccountNumber]`
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported. 
  
### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### RRP Price
_Optional_  
Allows you to specify the price list to use to export the RRP price from e.g. RRP Prices

### Standard Price
_Required_    
Lets you specify the price list used to export the standard price from. e.g. Standard 

### Output File
_Required_  
The file to save the exported records to, in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Products>
    <Product>
      <UniqueId>6688</UniqueId>
      <Sku>PROD001</Sku>
      <Barcode />
      <Name>Test Product</Name>
      <Description />
      <Status>1</Status>
      <SalePrice>8.325</SalePrice>
      <UnitWeight>0</UnitWeight>
      <QtyInStock>0</QtyInStock>
      <QtyOnOrder>36</QtyOnOrder>
      <ReorderQty xsi:nil="true" />
      <ReorderLvl>0</ReorderLvl>
      <TaxCode>1</TaxCode>
      <GroupCode>No Group</GroupCode>
      <GroupName>No Group</GroupName>
      <Department>6694</Department>
      <UnitOfSale>Each</UnitOfSale>
      <NominalCode />
      <Publish xsi:nil="true" />
      <ProductLevel>0</ProductLevel>
      <SpecialOffer xsi:nil="true" />
      <QtyAllocated>0</QtyAllocated>
      <LastCostPrice xsi:nil="true" />
      <LastCostPriceDiscounted xsi:nil="true" />
      <QtyLastOrder xsi:nil="true" />
      <AverageCostPrice>0</AverageCostPrice>
      <StandardCostPrice>0</StandardCostPrice>
      <RRPPrice>0</RRPPrice>
      <Attachments />
      <DateModified xsi:nil="true" />
      <InactiveDate xsi:nil="true" />
      <Dimensions />
      <ProductBoms />
      <RelatedProducts />
      <AlternativeProducts />
      <ProductQtyBreaks />
      <CommodityCode />
      <Manufacturer />
      <ManufacturerPartNo />
      <Locations />
      <AllowSalesOrder>true</AllowSalesOrder>
      <Attributes>
        <Attribute>
          <Name>Sync with website</Name>
          <Value>&lt;NONE&gt;</Value>
        </Attribute>
      </Attributes>
      <UnitsOfMeasure>
        <UnitOfMeasure>
          <Name>Each</Name>
          <Quantity>1</Quantity>
        </UnitOfMeasure>
      </UnitsOfMeasure>
      <UseDescriptionOnDocs>false</UseDescriptionOnDocs>
      <DefaultPickingListComment />
      <DefaultDespatchNoteComment />
      <BOMItemType>Component</BOMItemType>
      <ItemType>Stock</ItemType>
      <FulfilmentMethod>FromStock</FulfilmentMethod>
      <ProductSuppliers />
      <AnalysisCodes />
      <SearchCategories />
    </Product>
    <Product>
      <UniqueId>6429</UniqueId>
      <Sku>PROD002</Sku>
      <Barcode />
      <Name>Test Product 2</Name>
      <Description />
      <Status>1</Status>
      <SalePrice>220.8083</SalePrice>
      <UnitWeight>0</UnitWeight>
      <QtyInStock>9</QtyInStock>
      <QtyOnOrder>10</QtyOnOrder>
      <ReorderQty xsi:nil="true" />
      <ReorderLvl>0</ReorderLvl>
      <TaxCode>1</TaxCode>
      <GroupCode>No Group</GroupCode>
      <GroupName>No Group</GroupName>
      <Department>6435</Department>
      <UnitOfSale>Each</UnitOfSale>
      <NominalCode />
      <Publish xsi:nil="true" />
      <ProductLevel>0</ProductLevel>
      <SpecialOffer xsi:nil="true" />
      <QtyAllocated>0</QtyAllocated>
      <LastCostPrice xsi:nil="true" />
      <LastCostPriceDiscounted xsi:nil="true" />
      <QtyLastOrder xsi:nil="true" />
      <AverageCostPrice>0</AverageCostPrice>
      <StandardCostPrice>0</StandardCostPrice>
      <RRPPrice>0</RRPPrice>
      <Attachments />
      <DateModified xsi:nil="true" />
      <InactiveDate xsi:nil="true" />
      <Dimensions />
      <ProductBoms>
        <ProductBom>
          <UniqueId>40988</UniqueId>
          <Sku>PROD003</Sku>
          <Quantity>1</Quantity>
          <SequenceNumber>1</SequenceNumber>
          <UnitOfMeasure>Each</UnitOfMeasure>
        </ProductBom>
        <ProductBom>
          <UniqueId>40989</UniqueId>
          <Sku>PROD004</Sku>
          <Quantity>1</Quantity>
          <SequenceNumber>2</SequenceNumber>
          <UnitOfMeasure>Each</UnitOfMeasure>
        </ProductBom>
      </ProductBoms>
      <RelatedProducts />
      <AlternativeProducts />
      <ProductQtyBreaks />
      <CommodityCode />
      <Manufacturer />
      <ManufacturerPartNo />
      <Locations />
      <AllowSalesOrder>true</AllowSalesOrder>
      <Attributes>
        <Attribute>
          <Name>Sync with website</Name>
          <Value>&lt;NONE&gt;</Value>
        </Attribute>
      </Attributes>
      <UnitsOfMeasure>
        <UnitOfMeasure>
          <Name>Each</Name>
          <Quantity>1</Quantity>
        </UnitOfMeasure>
      </UnitsOfMeasure>
      <UseDescriptionOnDocs>false</UseDescriptionOnDocs>
      <DefaultPickingListComment />
      <DefaultDespatchNoteComment />
      <BOMItemType>Stocked Built Item</BOMItemType>
      <ItemType>Stock</ItemType>
      <FulfilmentMethod>FromStock</FulfilmentMethod>
      <ProductSuppliers />
      <AnalysisCodes />
      <SearchCategories />
    </Product>
  </Products>
</Company>
```
