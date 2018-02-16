---
slug: importing-products-to-brightpearl
redirect_from: "/article/179-uploading-products-to-brightpearl"
title: Importing Products to Brightpearl
---


This task will create new products in Brightpearl from an XML file. Please note that the task does not support updating existing products.


## Settings

### Connection 
_Required_
The Brightpearl connection to use. See [Connecting to Brightpearl](connecting-to-brightpearl)

### Fail File
_Required_
The file to save failed records to.

### Input File
_Required_
The file containing records to import.

### Success File
_Required_
The file to save successful records to.

### Prevent Reprocessing
_Required_
Set to true to prevent the same records being processed more than once, based on the value of the `externalId` element in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample input file containing the minimum information required to create a product:


```xml
<?xml version="1.0"?>
<ArrayOfProduct>
	<Product>
		<externalId>9346</externalId>
		<brand>
			<name>Other</name>
		</brand>
		<identity>
			<sku>ABC123</sku>
		</identity>
		<financialDetails>
			<taxCode>
				<code>T20</code>
			</taxCode>
		</financialDetails>
		<salesChannels>
			<salesChannel>
				<salesChannelName>Brightpearl</salesChannelName>
				<productName>Uploaded product</productName>
				<productCondition>new</productCondition>
				<description>
					<languageCode>en</languageCode>
					<text>Product description in here</text>
					<format>HTML_FRAGMENT</format>
				</description>
			</salesChannel>
		</salesChannels>
	</Product>
</ArrayOfProduct>
```