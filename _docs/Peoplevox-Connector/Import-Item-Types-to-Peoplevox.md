---
slug: import-item-types-to-peoplevox
title: Import Item Types to Peoplevox
---

This task will import item type information to Peoplevox in XML format, for detailed information see [Peoplevox Item Type XML](peoplevox-item-type-xml).  The information is imported using the standard fields under Integration Templates that can be configured through your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Integration Templates
### Item Type
[Download Template](/assets/resources/peoplevox/item_type.csv)

```csv
ItemCode,Name,Barcode,ItemGroup,RetailPrice,Description,UnitOfMeasure,DefaultEconomicOrderQuantity,DefaultLeadTime,DefaultSuppliersPartNumber,HasSerialNumbers,UseManufacturersSerialNumber,ReorderPoint,Traceability,ShelfLife,DefaultNumberItemsPerContainer,DefaultContainerType,DefaultNumberItemsPerOuterCase,DefaultNumberItemsPerInnerCase,BuyPrice,WholesalePrice,RetailPrice,Weight,WeightMeasure,Height,Width,Depth,DimensionMeasure,Tags,Attribute1,Attribute2,Attribute3,Attribute4,Attribute5,Attribute6,Attribute7,Attribute8,Attribute9,Attribute10,Attribute11,Attribute12,Attribute13,Attribute14,Attribute15,TaxCode,MinimumPickLocationQuantity,DefaultReplenishmentQuantity
```

### Item Type Group
[Download Template](/assets/resources/peoplevox/item_type_group.csv)

```csv
Name,ProductGroup
```

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### Input File
_Required_  
The name or full path to the file the data to be imported will be read from.  Defaults to `peoplevox_import_item_types.xml`, which should exist in the working directory of the Workflow.

### Success File
_Required_  
The name or full path to the file successfully imported records will be saved to.  Defaults to `peoplevox_import_item_types_success.xml`, which will be created in the working directory of the Workflow.

### Fail File
_Required_  
The name or full path to the file falied records will be saved to.  Defaults to `peoplevox_import_item_types_fail.xml`, which will be created in the working directory of the Workflow.

### Auto Create Item Groups
_Required_  
Set to False if you do not need item groups being created on Peoplevox as part of the import.  Set to True to allow Zynk create the item groups.  Note, Peoplevox will create any item groups that do not already exist regardless of this setting.  This setting works best when using the `ItemTypeGroup` object within the XML to allow you to set the parent group.

### Prevent Reprocessing
_Required_  
Set to true if you only want to process a record once, or false to update every time.  Defaults to False.

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

## Example XML
Example input file, for detailed information see [Peoplevox Item Type XML](peoplevox-item-type-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<ItemTypes 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
	xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<ItemType>
		<ItemCode>PROD001</ItemCode>
		<Name>Sample Product</Name>
		<Barcode>123456789</Barcode>
		<Description>Sample product for Peoplevox</Description>
		<ItemGroup>Stock</ItemGroup>
		<UnitOfMeasure>Unit</UnitOfMeasure>
		<DefaultEconomicOrderQuantity>1</DefaultEconomicOrderQuantity>
		<DefaultLeadTime>10</DefaultLeadTime>
		<DefaultSuppliersPartNumber>02TEST</DefaultSuppliersPartNumber>
		<HasSerialNumber>true</HasSerialNumber>
		<UseManufacturersSerialNumber>true</UseManufacturersSerialNumber>
		<ReorderPoint>1</ReorderPoint>
		<Traceability>true</Traceability>
		<ShelfLife>2017-04-10T00:00:00</ShelfLife>
		<DefaultNumberOfItemsPerContainer>1</DefaultNumberOfItemsPerContainer>
		<DefaultContainerType>test</DefaultContainerType>
		<DefaultNumberItemsPerOuterCase>1</DefaultNumberItemsPerOuterCase>
		<BuyPrice>1</BuyPrice>
		<WholesalePrice>2</WholesalePrice>
		<RetailPrice>3</RetailPrice>
		<Weight>1</Weight>
		<WeightMeasure>Pounds</WeightMeasure>
		<Height>1</Height>
		<Width>1</Width>
		<Depth>1</Depth>
		<DimensionMeasure>Inches</DimensionMeasure>
		<Tags>stock</Tags>
		<Attribute1>attribute_1</Attribute1>
		<Attribute2>attribute_2</Attribute2>
		<Attribute3>attribute_3</Attribute3>
		<ItemTypeGroup>
			<Name>Stock</Name>
			<ParentGroup>Items</ParentGroup>
		</ItemTypeGroup>
	</ItemType>
</ItemTypes>
```