---
slug: updating-order-statuses-in-magento-v2
redirect_from: "/article/771-updating-order-statuses-in-magento"
title: Updating Order Statuses in Magento V2
---
This task will update order statuses in Magento, and optionally add a comment. See below for a sample input file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

## Fail File
_Required_  
The XML file to save failed order updates to. The data will be written in the same format as the input file.

## Input File
_Required_  
The XML file containing the orders to be updated in Magento.

## Success File
_Required_  
The XML file to save successful order updates to. The data will be written in the same format as the input file.

## Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. This will change the status of order 000000001 to 'Processing', and add a comment.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfOrderStatusHistory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <OrderStatusHistory>
    <parent_id>1</parent_id>
    <parent_increment_id>000000001</parent_increment_id>
    <status>processing</status>
    <comment>Order imported into Sage</comment>
  </OrderStatusHistory>
</ArrayOfOrderStatusHistory>
```

Sample XSLT file to use to transform orders exported from Sage in the Zynk XML Sales Orders format, to the Magento order update format. This is also available in the [Auto Mapper](auto-mapper).
```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
    
    <xsl:output method="xml" indent="yes"/>

    <xsl:param name="Status" /><!-- Required - Enter the status to set in Magento -->
    <xsl:param name="Comment" /><!-- Optional - Enter the comment to set in Magento -->
    
    <xsl:template match="Company">
        <ArrayOfOrderStatusHistory>
            <xsl:for-each select="SalesOrders/SalesOrder">
                <xsl:call-template name="OrderInfo" />
            </xsl:for-each>
        </ArrayOfOrderStatusHistory>
    </xsl:template>
    
    <xsl:template name="OrderInfo">
        <OrderStatusHistory>
            <parent_increment_id><xsl:value-of select="CustomerOrderNumber" /></parent_increment_id>
            <status><xsl:value-of select="$Status" /></status>
    
            <xsl:if test="$Comment != ''">
                <comment><xsl:value-of select="$Comment" /></comment>
            </xsl:if>
        </OrderStatusHistory>
    </xsl:template>
    
</xsl:stylesheet>
```
