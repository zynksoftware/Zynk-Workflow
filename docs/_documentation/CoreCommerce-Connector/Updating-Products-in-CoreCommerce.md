---
slug: updating-products-in-corecommerce
redirect_from: "/article/191-updating-products-in-corecommerce"
title: Updating Products in CoreCommerce
---
This task will update the existing products in CoreCommerce. Note that it does not support the creation of new products. The products in the input file are matched to existing products in CoreCommerce based on either the product ID or SKU code.

## Settings
### Connection
_Required_  
The CoreCommerce connection to use. See the [Connecting to CoreCommerce](connecting-to-corecommerce) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The file to save any failed product updates to.

### Input File
_Required_  
The file containing the products to update. The data must be in the CoreCommerce XML format, an example is shown below.

### Success File
_Required_  
The file to save successful product updates to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Core Commerce to Sage 50 Integration](core-commerce-to-sage-50-integration) article.

Sample input file, which will update the price and stock level of the products with SKU code PROD001 and PROD002:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductList>
	<Product>
		<Sku>PROD001</Sku>
		<Price>
			<Amount>12.00</Amount>
		</Price>
		<InventoryLevel>52</InventoryLevel>
	</Product>
	<Product>
		<Sku>PROD002</Sku>
		<Price>
			<Amount>11.59</Amount>
		</Price>
		<InventoryLevel>30</InventoryLevel>
	</Product>
</ProductList>
```

Sample success file, showing that product ID 8 (PROD001) was updated:
```xml
<?xml version="1.0"?>
<ProductResponseList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Product id="8">
		<Code>100</Code>
		<Message />
	</Product>
</ProductResponseList>
```

Sample fail file, showing that the product PROD002 was not updated, because it does not exist:
```xml
<?xml version="1.0"?>
<ProductResponseList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Product>
		<Code />
		<Message>No product with SKU 'PROD002' was found in CoreCommerce.</Message>
	</Product>
</ProductResponseList>
```