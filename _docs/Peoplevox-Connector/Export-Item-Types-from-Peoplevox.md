---
slug: export-item-types-from-peoplevox
title: Export Item Types from Peoplevox
---

This task will export item type information from Peoplevox in XML format, for detailed information see [Peoplevox Item Type XML](peoplevox-item-type-xml).  The information is exported using the "Item types" report that can be ran through your Peoplevox web application.  You can add date filters and search clauses to limit the data that is returned.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### API Call Delay
_Required_  
The number of seconds to wait between sending requests to the Peoplevox API, used when making multiple paged requests to export data.  Defaults to 1.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_item_types.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Zynk Settings
See [Common Task Settings](common-task-settings)

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