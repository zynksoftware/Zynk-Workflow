---
slug: uploading-tier-prices-to-magento
redirect_from: "/article/273-uploading-tier-prices-to-magento"
title: Uploading Tier Prices to Magento
---
This task will update price list data for the products in Magento, note this uploads to Tier Prices not Group Prices. To upload Group Prices, use the [Uploading Group Prices to Magento](uploading-group-prices-to-magento) task instead. The price list names in the XML file must match the name of customers groups in Magento. See attachments for sample file.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed price updates to.

### Input File
_Required_  
The XML file containing the products to update prices for.

### Success File
_Required_  
The XML file to output successful price updates to.

### Standard Price List
_Required_  
The name of the price list from Sage to use for the standard selling price of the product. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file, showing the product BOARD001 and a single tier price for the customer group 'A1 Design Services':
```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<ArrayOfProductPrice>
  <ProductPrice>
    <sku>BOARD001</sku>
    <prices>
      <ProductTierPrice>
        <customer_group_id>A1 Design Services</customer_group_id>
        <qty>1</qty>
        <price>18</price>
      </ProductTierPrice>
    </prices>
  </ProductPrice>
</ArrayOfProductPrice>
```

Sample XSLT file to use to transform price lists exported from Sage in the Zynk XML format, to the Magento tier price format. This is also available in the [Auto Mapper](auto-mapper).
```xml
<?xml version="1.0" encoding="iso-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="xml" standalone="yes" indent="yes" />
  <xsl:key name="UniqueSku" match="Company/PriceLists/PriceList/Prices/Price" use="StockCode" />

  <xsl:template match="/">
    <ArrayOfProductPrice>
      <xsl:for-each select="//Company/PriceLists/PriceList/Prices/Price[generate-id() = generate-id(key('UniqueSku', StockCode)[1])]">
        <xsl:call-template name="ProductPrice" />
      </xsl:for-each>
    </ArrayOfProductPrice>
  </xsl:template>

  <xsl:template name="ProductPrice">
    <ProductPrice>
      <sku><xsl:value-of select="StockCode" /></sku>
      <prices>
        <xsl:call-template name="TierPrices">
          <xsl:with-param name="StockCode" select="StockCode" />
        </xsl:call-template>
      </prices>
    </ProductPrice>
  </xsl:template>

  <xsl:template name="TierPrices">
    <xsl:param name="StockCode" />

    <xsl:for-each select="../../../PriceList/Prices/Price[StockCode=$StockCode]">
      <xsl:call-template name="TierPrice" />
    </xsl:for-each>
  </xsl:template>

  <xsl:template name="TierPrice">
    <xsl:if test="StoredPrice > 0">
      <ProductTierPrice>
        <customer_group_id><xsl:value-of select="../../Name" /></customer_group_id>
        <qty>1</qty>
        <price><xsl:value-of select="StoredPrice" /></price>
      </ProductTierPrice>
    </xsl:if>
  </xsl:template>

</xsl:stylesheet>
```