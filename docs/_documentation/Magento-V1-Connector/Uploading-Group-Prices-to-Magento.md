---
slug: uploading-group-prices-to-magento
redirect_from: "/article/268-uploading-group-prices-to-magento"
title: Uploading Group Prices to Magento
---
This is an overview of the Upload Group Prices task. Depending on how the pricing system works on your Magento site, you may need to use the [Uploading Tier Prices to Magento](uploading-tier-prices-to-magento) task instead.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output successful price updates to.

### Input File
_Required_  
The XML file containing the group prices to upload to Magento.

### Success File
_Required_  
The XML file to output successful price updates to.

### Standard Price List
_Required_  
The common price list on your Magento website.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file with two group prices for the product BOARD001 is shown below.
```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<ArrayOfProduct>
  <Product>
    <sku>BOARD001</sku>
    <group_price>
      <ProductGroupPrice>
        <website_id>0</website_id>
        <all_groups>0</all_groups>
        <cust_group>TRADEA</cust_group>
        <price>19</price>
      </ProductGroupPrice>
      <ProductGroupPrice>
        <website_id>0</website_id>
        <all_groups>0</all_groups>
        <cust_group>TRADEB</cust_group>
        <price>18</price>
      </ProductGroupPrice>
    </group_price>
  </Product>
</ArrayOfProduct>
```

A sample XSLT for transforming Zynk XML prices to Magento group prices is shown below. This is also available in the [Auto Mapper](auto-mapper) task.
```xml
<?xml version="1.0" encoding="iso-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="xml" standalone="yes" indent="yes" />
  <xsl:key name="UniqueSku" match="Company/PriceLists/PriceList/Prices/Price" use="StockCode" />

  <xsl:template match="/">
    <ArrayOfProduct>
      <xsl:for-each select="//Company/PriceLists/PriceList/Prices/Price[generate-id() = generate-id(key('UniqueSku', StockCode)[1])]">
        <xsl:call-template name="ProductPrice" />
      </xsl:for-each>
    </ArrayOfProduct>
  </xsl:template>

  <xsl:template name="ProductPrice">
    <Product>
      <sku><xsl:value-of select="StockCode" /></sku>
      <group_price>
        <xsl:call-template name="GroupPrices">
          <xsl:with-param name="StockCode" select="StockCode" />
        </xsl:call-template>
      </group_price>
    </Product>
  </xsl:template>

  <xsl:template name="GroupPrices">
    <xsl:param name="StockCode" />
      <xsl:for-each select="../../../PriceList/Prices/Price[StockCode=$StockCode]">
        <xsl:call-template name="GroupPrice" />
      </xsl:for-each>
    </xsl:template>

  <xsl:template name="GroupPrice">        
    <xsl:if test="StoredPrice > 0">
      <ProductGroupPrice>
        <website_id>0</website_id>
        <all_groups>0</all_groups>
        <cust_group><xsl:value-of select="../../Name" /></cust_group>
        <price><xsl:value-of select="StoredPrice" /></price>
      </ProductGroupPrice>
    </xsl:if>
  </xsl:template>

</xsl:stylesheet>
```