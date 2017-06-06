---
slug: updating-inventory-in-bigcommerce
redirect_from: "/article/170-updating-inventory-in-bigcommerce"
title: Updating Inventory in BigCommerce
---
This task will update stock levels of products and option SKUs in your BigCommerce store.

## Settings
### Connection
_Required_  
The BigCommerce connection to use. See the [Connecting to BigCommerce](connecting-to-bigcommerce) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed updates to.

### Input File
_Required_  
The XML file containing the inventory updates. The products will be matched based on the  <sku> provided. If no matching option SKU is found, the task will look for a product with a matching SKU. The task can update both the stock level and stock warning level.

### Success File
_Required_  
The XML file to output successful updates to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [BigCommerce to Sage 50 Integration](bigcommerce-to-sage-50-integration) article.

Sample input file which will update the stock level of the product FAX001 to 2:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInventory>
	<Inventory>
		<sku>FAX001</sku>
		<inventory_level>2</inventory_level>
		<inventory_warning_level>0</inventory_warning_level>
	</Inventory>
</ArrayOfInventory>
```

Sample XSLT file to use to transform products exported from Sage in the Zynk XML Products format, to the BigCommerce inventory update format. This is also available in the [Auto Mapper](auto-mapper).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

	<xsl:output method="xml" indent="yes" />

	<xsl:template match="/">
		<ArrayOfInventory>
			<xsl:for-each select="Company/Products/Product">
				<xsl:call-template name="Inventory" />
			</xsl:for-each>
		</ArrayOfInventory>
	</xsl:template>

	<xsl:template name="Inventory">
		<Inventory>
			<sku><xsl:value-of select="Sku" /></sku>

			<inventory_level>
				<xsl:choose>
					<xsl:when test="(QtyInStock - QtyAllocated) < 1">
						<xsl:text>0</xsl:text>
					</xsl:when>
					<xsl:otherwise>
						<xsl:value-of select="QtyInStock - QtyAllocated" />
					</xsl:otherwise>
				</xsl:choose>
			</inventory_level>

			<inventory_warning_level>
				<xsl:value-of select="ReorderLvl" />
			</inventory_warning_level>
		</Inventory>
	</xsl:template>

</xsl:stylesheet>
```