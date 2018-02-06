---
slug: uploading-products-to-magento-v2
redirect_from: "/article/773-uploading-products-to-magento"
title: Uploading Products to Magento V2
---
 This task will create or update products in Magento. See below for a sample input file.

If the `<id>` element is specified in the input file, the task will update the product with the specified ID. If no ID is specified, the task will use the `<sku>` element to check if the product already exists. If a match is found the existing product will be updated, otherwise a new product will be created.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

## Fail File
_Required_  
The XML file to save failed product uploads to. The data will be written in the same format as the input file.

## Input File
_Required_  
The XML file containing the products to upload in Magento.

## Success File
_Required_  
The XML file to save successful product uploads to. The data will be written in the same format as the input file.

## Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. This will update the product with SKU code '24-MB01'.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfProduct xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <id>1</id>
    <sku>24-MB01</sku>
    <name>Joust Duffle Bag</name>
    <store_id xsi:nil="true" />
    <attribute_set_id>15</attribute_set_id>
    <price>34</price>
    <status>1</status>
    <visibility>4</visibility>
    <type_id>simple</type_id>
    <weight xsi:nil="true" />
    <product_links>
      <product_link>
        <sku>24-MB01</sku>
        <link_type>upsell</link_type>
        <linked_product_sku>24-MB03</linked_product_sku>
        <linked_product_type>simple</linked_product_type>
        <position xsi:nil="true" />
        <extension_attributes />
      </product_link>
      <product_link>
        <sku>24-MB01</sku>
        <link_type>upsell</link_type>
        <linked_product_sku>24-MB05</linked_product_sku>
        <linked_product_type>simple</linked_product_type>
        <position xsi:nil="true" />
        <extension_attributes />
      </product_link>
    </product_links>
    <options />
    <tier_prices />
    <custom_attributes>
      <custom_attribute>
        <attribute_code>description</attribute_code>
        <value><p>The sporty Joust Duffle Bag can't be beat - not in the gym, not on the luggage carousel, not anywhere. Big enough to haul a basketball or soccer ball and some sneakers with plenty of room to spare, it's ideal for athletes with places to go.<p>
<ul>
<li>Dual top handles.</li>
<li>Adjustable shoulder strap.</li>
<li>Full-length zipper.</li>
<li>L 29" x W 13" x H 11".</li>
</ul></value>
      </custom_attribute>
      <custom_attribute>
        <attribute_code>image</attribute_code>
        <value>/m/b/mb01-blue-0.jpg</value>
      </custom_attribute>
    </custom_attributes>
  </Product>
</ArrayOfProduct>
```

Sample XSLT file to use to transform products exported from Sage in the Zynk XML Products format, to the Magento product format. This is also available in the [Auto Mapper](auto-mapper).
```xml
<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="xml" indent="yes"/>
  <xsl:param name="AttributeSet">4</xsl:param>

  <xsl:template match="/">
    <ArrayOfProduct>
      <xsl:for-each select="Company/Products/Product">
        <xsl:call-template name="Product" />
      </xsl:for-each>
    </ArrayOfProduct>
  </xsl:template>

  <xsl:template name="Product">
    <Product>
      <sku><xsl:value-of select="Sku" /></sku>
      <name><xsl:value-of select="Name" /></name>
      <qty><xsl:value-of select="QtyInStock - QtyAllocated" /></qty>
      <type>simple</type>
      <set><xsl:value-of select="$AttributeSet" /></set>
      <websites>1</websites>
      <status>1</status>
      <price><xsl:value-of select="SalePrice" /></price>

      <is_in_stock>
        <xsl:choose>
          <xsl:when test="(QtyInStock - QtyAllocated) > 0">1</xsl:when>
          <xsl:otherwise>0</xsl:otherwise>
        </xsl:choose>
      </is_in_stock>

      <custom_attributes>
        <custom_attribute>
          <attribute_code>description</attribute_code>
          <value><xsl:value-of select="Description"/></value>
        </custom_attribute>
        <custom_attribute>
          <attribute_code>tax_class_id</attribute_code>
          <value>
            <xsl:choose>
              <xsl:when test="TaxCode = '1'">2</xsl:when>
              <xsl:otherwise>0</xsl:otherwise>
            </xsl:choose>
          </value>
        </custom_attribute>
      </custom_attributes>
    </Product>
  </xsl:template>
</xsl:stylesheet>
```
