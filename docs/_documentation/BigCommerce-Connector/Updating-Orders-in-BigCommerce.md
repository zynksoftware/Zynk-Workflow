---
slug: updating-orders-in-bigcommerce
redirect_from: "/article/171-updating-orders-in-bigcommerce"
title: Updating Orders in BigCommerce
---
This task will change the status of orders in your BigCommerce store. It can be used in conjunction with the Download Stage setting on the [Downloading Orders from BigCommerce](downloading-orders-from-bigcommerce) task, to change the status of orders once they have been processed to prevent them downloading again.

## Settings
### Connection
_Required_  
The BigCommerce connection to use. See the [Connecting to BigCommerce](connecting-to-bigcommerce) article if you require more information on how to create/manage connections.

### Input File
_Required_  
The XML file containing the orders to update. These should be stored in the same format as orders downloaded using the 'Download Orders' task, but the only required information is the  <id> of the orders.

### Notify Stage
_Required_  
The status to change the orders to. Defaults to 'Completed'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [BigCommerce to Sage 50 Integration](bigcommerce-to-sage-50-integration) article.

Sample input file which will update the status of order 105 to the status selected in the 'Notify Stage' setting.

```xml
<?xml version="1.0" encoding="utf-8"?>
<orders>
	<order>
		<id>105</id>
	</order>
</orders>
```

Sample XSLT file to use to transform orders exported from Sage in the Zynk XML Sales Orders format, to the BigCommerce order update format. This is also available in the [Auto Mapper](auto-mapper).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
	<xsl:output method="xml" indent="yes"/>
	<xsl:template match="/">
		<orders>
			<xsl:for-each select="Company/SalesOrders/SalesOrder">
				<order>
					<id>
						<xsl:value-of select="Id" />
					</id>
				</order>
			</xsl:for-each>
		</orders>
	</xsl:template>
</xsl:stylesheet>
```