---
slug: uploading-inventory-to-magento
redirect_from: "/article/269-uploading-inventory-to-magento"
title: Uploading Inventory to Magento
---
This task will update stock data for the products in Magento.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed stock level updates to.

### Input File
_Required_  
The XML file containing the products to update stock levels for.

### Success File
_Required_  
The XML to output successful stock level updates to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file, showing the product TEST with a stock level of 80:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInventory>
  <Inventory>
    <sku>TEST</sku>
    <qty>80</qty>
    <is_in_stock>1</is_in_stock>
  </Inventory>
</ArrayOfInventory>
```

Sample XSLT file to use to transform products exported from Sage in the Zynk XML Products format, to the Magento order update format. This is also available in the [Auto Mapper](auto-mapper).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="xml" version="1.0" encoding="utf-8" indent="yes"/>

  <xsl:template match="/">
    <ArrayOfInventory>
      <xsl:for-each select="Company/Products/Product">
        <xsl:call-template name="Product" />
      </xsl:for-each>
    </ArrayOfInventory>
  </xsl:template>

  <xsl:template name="Product">
    <xsl:choose>
      <!-- Don't allow negative stock levels -->
      <xsl:when test="(QtyInStock - QtyAllocated) > -1">
        <Inventory>
          <sku><xsl:value-of select="Sku"/></sku>
          <qty><xsl:value-of select="(QtyInStock - QtyAllocated)"/></qty>
          <is_in_stock>
            <xsl:call-template name="IsInStock">
              <xsl:with-param name="QtyInStock" select="QtyInStock" />
              <xsl:with-param name="QtyAllocated" select="QtyAllocated" />
            </xsl:call-template>
          </is_in_stock>
        </Inventory>
      </xsl:when>
    </xsl:choose>
  </xsl:template>

  <xsl:template name="IsInStock">
    <xsl:param name="QtyInStock"/>
    <xsl:param name="QtyAllocated"/>
    <xsl:choose>
      <xsl:when test="($QtyInStock - $QtyAllocated) > 0">1</xsl:when>
      <xsl:otherwise>0</xsl:otherwise>
    </xsl:choose>
  </xsl:template>

</xsl:stylesheet>
```