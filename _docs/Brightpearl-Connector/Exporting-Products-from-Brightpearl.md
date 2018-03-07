---
slug: exporting-products-from-brightpearl
redirect_from: "/article/176-downloading-products-from-brightpearl"
title: Exporting Products from Brightpearl
---


This task will download products from Brightpearl in XML format.


## Settings

### Connection
_Required_
The Brightpearl connection to use.

### Product Status 
_Optional_
Enter a product status to filer the export on.

### Output File
_Required_
The file to save exported records to.

### Brightpearl Settings
See [Common Brightpearl Settings](common-brightpearl-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample output file:


```xml
<?xml version="1.0"?>
<ArrayOfProduct>
	<Product>
		<externalId />
		<createdOn>2016-11-18T16:06:12Z</createdOn>
		<updatedOn>2016-11-18T16:36:34Z</updatedOn>
		<id>1007</id>
		<brand>
			<id>74</id>
			<name>Other</name>
			<description />
		</brand>
		<productType>
			<id>1</id>
			<name>Default</name>
			<associations>
				<options>
					<Option>
						<id>1</id>
						<name>Colour</name>
					</Option>
					<Option>
						<id>2</id>
						<name>Size</name>
					</Option>
				</options>
			</associations>
		</productType>
		<seasons />
		<productGroupId xsi:nil="true" />
		<nominalCodeStock>1001</nominalCodeStock>
		<identity>
			<sku>IPHONE</sku>
			<barcode />
		</identity>
		<stock>
			<stockTracked>true</stockTracked>
			<weight>
				<magnitude>0</magnitude>
			</weight>
		</stock>
		<financialDetails>
			<taxable>false</taxable>
			<taxCode>
				<id>7</id>
				<code>T20</code>
				<description>VAT</description>
				<rate>20</rate>
			</taxCode>
		</financialDetails>
		<salesChannels>
			<salesChannel>
				<id xsi:nil="true" />
				<salesChannelName>Brightpearl</salesChannelName>
				<productName>iPhone</productName>
				<productCondition>new</productCondition>
				<categories>
					<Category>
						<categoryCode>276</categoryCode>
					</Category>
				</categories>
				<description>
					<languageCode>en</languageCode>
					<text />
					<format>HTML_FRAGMENT</format>
				</description>
				<shortDescription>
					<languageCode>en</languageCode>
					<text>
						<p>An iphone</p>
					</text>
					<format>HTML_FRAGMENT</format>
				</shortDescription>
				<availableToSellOnChannel xsi:nil="true" />
				<sellwhenNoStock xsi:nil="true" />
			</salesChannel>
		</salesChannels>
		<composition>
			<bundle>false</bundle>
		</composition>
		<variations>
			<variation>
				<optionId>1</optionId>
				<optionName>Colour</optionName>
				<optionValueId>2</optionValueId>
				<optionValue>White</optionValue>
			</variation>
		</variations>
		<warehouses>
			<item>
				<key>2</key>
				<value>
					<defaultLocationId>0</defaultLocationId>
					<reorderLevel>0</reorderLevel>
					<reorderQuantity>5</reorderQuantity>
				</value>
			</item>
		</warehouses>
		<customFields />
	</Product>
</ArrayOfProduct>
```
