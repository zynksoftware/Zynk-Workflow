---
slug: importing-special-prices-to-magento-v2
title: Importing Special Prices into Magento v2
---

This task will add and update special prices in Magento v2. You must provide a sku (as shown in XML example below) that exists in Magento v2 for the special price to update successfully.

## API Endpoint
##### [POST /V1/products/special-price](https://devdocs.magento.com/redoc/2.3/admin-rest-api.html#tag/productsspecial-price)  

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to save failed special price imports to. The data will be written in the same format as the input file.

### Input File
_Required_  
The XML file containing the special price to import in Magento.

### Success File
_Required_  
The XML file to save successful special price imports to. The data will be written in the same format as the input file.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfSpecialPrice>
	<SpecialPrice>
		<sku>24-MB01-9</sku>
		<price>10</price>
		<price_from>2019-11-15</price_from>
		<price_to>2019-11-18</price_to>
	</SpecialPrice>
</ArrayOfSpecialPrice>
```