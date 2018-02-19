---
slug: peoplevox-item-type-xml
title: Peoplevox Item Type XML
---

Zynk will import the data using the standard fields under Integration Templates that can be ran configured your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Tasks

 * [Import Item Types to Peoplevox](import-item-types-to-peoplevox)

## Integration Templates
### Item Type
[Download Template](/assets/resources/peoplevox/item_type.csv)

```csv
ItemCode,Name,Barcode,ItemGroup,RetailPrice,Description,UnitOfMeasure,DefaultEconomicOrderQuantity,DefaultLeadTime,DefaultSuppliersPartNumber,HasSerialNumbers,UseManufacturersSerialNumber,ReorderPoint,Traceability,ShelfLife,DefaultNumberItemsPerContainer,DefaultContainerType,DefaultNumberItemsPerOuterCase,DefaultNumberItemsPerInnerCase,BuyPrice,WholesalePrice,RetailPrice,Weight,WeightMeasure,Height,Width,Depth,DimensionMeasure,Tags,Attribute1,Attribute2,Attribute3,TaxCode,MinimumPickLocationQuantity,DefaultReplenishmentQuantity
```

### Item Type Group
[Download Template](/assets/resources/peoplevox/item_type_group.csv)

```csv
Name,ProductGroup
```

## Identifiers
For inserting or updating records to Peoplevox Zynk uses the ItemCode field on an ItemType.  It is invalid to insert / update an ItemType without providing the ItemCode.

## Fields
### ItemCode
_Required_  
Item code.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | PROD001 | `<ItemCode>PROD001</ItemCode>` |

### Name
_Optional_  
Name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Sample Product | `<Name>Sample Product</Name>` |

### Barcode
_Required_  
Barcode.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | 123456789 | `<Barcode>123456789</Barcode>` |

### Description
_Optional_  
Description.

| Type | Example | XML |
| --- | --- | --- |
| string(250) | Sample product for Peoplevox | `<Description>Sample product for Peoplevox</Description>` |

### ItemGroup
_Optional (see also [ItemTypeGroup](#ItemTypeGroup))_  
Item type group name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Stock | `<ItemGroup>Stock</ItemGroup>` |

### UnitOfMeasure
_Optional_  
Unit of measure (optional, EA by default).

| Type | Example | XML |
| --- | --- | --- |
| string(10) | 0191 303 7279 | `<UnitOfMeasure>Unit</UnitOfMeasure>` |

### DefaultEconomicOrderQuantity
_Optional_  
Default economic order quantity.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<DefaultEconomicOrderQuantity>1</DefaultEconomicOrderQuantity>` |

### DefaultLeadTime
_Optional_  
Default lead time.

| Type | Example | XML |
| --- | --- | --- |
| int | 10 | `<DefaultLeadTime>10</DefaultLeadTime>` |

### DefaultSuppliersPartNumber
_Optional_  
Suppliers part number.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | 02TEST | `<DefaultSuppliersPartNumber>02TEST</DefaultSuppliersPartNumber>` |

### HasSerialNumber
_Optional_  
Has serial number flag, false by default.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<HasSerialNumber>true</HasSerialNumber>` |

#### Available Values
 * true
 * false

### UseManufacturersSerialNumber
_Optional_  
Use manufacturerss serial number flag, false by default.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<UseManufacturersSerialNumber>true</UseManufacturersSerialNumber>` |

#### Available Values
 * true
 * false

### ReorderPoint
_Optional_  
Reorder point.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<ReorderPoint>1</ReorderPoint>` |

### Traceability
_Optional_  
Traceability flag, false by default.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<Traceability>true</Traceability>` |

#### Available Values
 * true
 * false

### ShelfLife
_Optional_  
Date in yyyy-MM-dd HH:mm:ss format.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-04-10T00:00:00 | `<ShelfLife>2017-04-10T00:00:00</ShelfLife>` |

### DefaultNumberItemsPerContainer
_Optional_  
Default number items per container.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<DefaultNumberOfItemsPerContainer>1</DefaultNumberOfItemsPerContainer>` |

### DefaultContainerType
_Optional_  
Default container type.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | test | `<DefaultContainerType>test</DefaultContainerType>` |

### DefaultNumberItemsPerOuterCase
_Optional_  
Default number items per outer case.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<DefaultNumberItemsPerOuterCase>1</DefaultNumberItemsPerOuterCase>` |

### BuyPrice
_Optional_  
Buy price.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 1 | `<BuyPrice>1</BuyPrice>` |

### WholesalePrice
_Optional_  
Wholesale price.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 2 | `<WholesalePrice>2</WholesalePrice>` |

### RetailPrice
_Optional_  
Retail price.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 3 | `<RetailPrice>3</RetailPrice>` |

### Weight
_Optional_  
Weight.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 1 | `<Weight>1</Weight>` |

### WeightMeasure
_Optional_  
Weight measure.

| Type | Example | XML |
| --- | --- | --- |
| string(10) | Pounds | `<WeightMeasure>Pounds</WeightMeasure>` |

### Height
_Optional_  
Height.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 1 | `<Height>1</Height>` |

### Width
_Optional_  
Width.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 1 | `<Width>1</Width>` |

### Depth
_Optional_  
Depth.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 1 | `<Depth>1</Depth>` |

### DimensionMeasure
_Optional_  
Dimension measure.

| Type | Example | XML |
| --- | --- | --- |
| string(10) | Inches | `<DimensionMeasure>Inches</DimensionMeasure>` |

### Tags
_Optional_  
Tags.

| Type | Example | XML |
| --- | --- | --- |
| string(8000) | stock | `<Tags>stock</Tags>` |

### Attribute1
_Optional_  
Attribute 1.

| Type | Example | XML |
| --- | --- | --- |
| string(500) | attribute_1 | `<Attribute1>attribute_1</Attribute1>` |

### Attribute2
_Optional_  
Attribute 2.

| Type | Example | XML |
| --- | --- | --- |
| string(500) | attribute_2 | `<Attribute2>attribute_2</Attribute2>` |

### Attribute3
_Optional_  
Attribute 3.

| Type | Example | XML |
| --- | --- | --- |
| string(500) | attribute_2 | `<Attribute3>attribute_3</Attribute3>` |

### ItemTypeGroup
_Optional (see also [ItemGroup](#ItemGroup))_  
Item type group.

#### Name
_Optional_  
Item type group name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Stock | `<Name>Stock</Name>` |

#### ParentGroup
_Optional_  
Parent item type group name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Items | `<ParentGroup>Items</ParentGroup>` |

## Example XML

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
		<DimensionMeasure>test</DimensionMeasure>
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