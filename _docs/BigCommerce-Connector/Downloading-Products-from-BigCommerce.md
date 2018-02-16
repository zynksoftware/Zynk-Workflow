---
slug: downloading-products-from-bigcommerce
redirect_from: "/article/169-downloading-products-from-bigcommerce"
title: Downloading Products from BigCommerce
---
This task will download products from your BigCommerce store to an XML file.

## Settings
### Connection
_Required_  
The BigCommerce connection to use. See the [Connecting to BigCommerce](connecting-to-bigcommerce) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all products from your store, or set to false to download only new or modified products since this task last ran. Defaults to False.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. products.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file showing the product 'FX010 Plain Paper Fax':

```xml
<?xml version="1.0" encoding="utf-8"?>
<products>
  <product>
    <id>101</id>
    <keyword_filter>NULL</keyword_filter>
    <name>FX010 Plain Paper Fax</name>
    <type>physical</type>
    <sku>FAX001</sku>
    <description>FX010 Plain Paper Fax</description>
    <search_keywords>NULL</search_keywords>
    <availability_description></availability_description>
    <price>180.0000</price>
    <cost_price>0.0000</cost_price>
    <retail_price>0.0000</retail_price>
    <sale_price>0.0000</sale_price>
    <calculated_price>180.0000</calculated_price>
    <sort_order>0</sort_order>
    <is_visible>false</is_visible>
    <is_featured>false</is_featured>
    <related_products></related_products>
    <inventory_level>0</inventory_level>
    <inventory_warning_level>0</inventory_warning_level>
    <warranty>NULL</warranty>
    <weight>0.0000</weight>
    <width>0.0000</width>
    <height>0.0000</height>
    <depth>0.0000</depth>
    <fixed_cost_shipping_price>0.0000</fixed_cost_shipping_price>
    <is_free_shipping>false</is_free_shipping>
    <inventory_tracking>simple</inventory_tracking>
    <rating_total>0</rating_total>
    <rating_count>0</rating_count>
    <total_sold>0</total_sold>
    <date_created>Mon, 24 Jun 2013 12:29:17 +0000</date_created>
    <brand_id>0</brand_id>
    <view_count>0</view_count>
    <page_title></page_title>
    <meta_keywords>NULL</meta_keywords>
    <meta_description>NULL</meta_description>
    <layout_file></layout_file>
    <is_price_hidden>false</is_price_hidden>
    <price_hidden_label></price_hidden_label>
    <categories>
      <value>18</value>
    </categories>
    <date_modified>Fri, 09 Aug 2013 13:28:15 +0000</date_modified>
    <event_date_field_name></event_date_field_name>
    <event_date_type>none</event_date_type>
    <event_date_start></event_date_start>
    <event_date_end></event_date_end>
    <myob_asset_account></myob_asset_account>
    <myob_income_account></myob_income_account>
    <myob_expense_account></myob_expense_account>
    <peachtree_gl_account></peachtree_gl_account>
    <condition>New</condition>
    <is_condition_shown>false</is_condition_shown>
    <preorder_release_date></preorder_release_date>
    <is_preorder_only>false</is_preorder_only>
    <preorder_message></preorder_message>
    <order_quantity_minimum>0</order_quantity_minimum>
    <order_quantity_maximum>0</order_quantity_maximum>
    <open_graph_type>product</open_graph_type>
    <open_graph_title></open_graph_title>
    <open_graph_description></open_graph_description>
    <is_open_graph_thumbnail>true</is_open_graph_thumbnail>
    <upc></upc>
    <date_last_imported></date_last_imported>
    <option_set_id>NULL</option_set_id>
    <tax_class_id>0</tax_class_id>
    <option_set_display>right</option_set_display>
    <bin_picking_number></bin_picking_number>
    <custom_url>/fx010-plain-paper-fax/</custom_url>
    <availability>available</availability>
    <brand></brand>
    <images></images>
    <discount_rules></discount_rules>
    <configurable_fields></configurable_fields>
    <custom_fields></custom_fields>
    <videos></videos>
    <skus></skus>
    <rules></rules>
    <option_set>NULL</option_set>
    <options></options>
    <tax_class>
      <taxclass>
        <id>1</id>
        <name>Non-Taxable Products</name>
      </taxclass>
      <taxclass>
        <id>2</id>
        <name>Shipping</name>
      </taxclass>
      <taxclass>
        <id>3</id>
        <name>Gift Wrapping</name>
      </taxclass>
    </tax_class>
  </product>
</products>
```

Sample XSLT file to use to transform the output file from this task to the Zynk XML Products format, ready for import into Sage. This is also available in the [Auto Mapper](auto-mapper).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">
  <xsl:output method="xml" indent="yes"/>

  <xsl:template match="/">
    <Company>
      <Products>
        <xsl:for-each select="products/product">
          <xsl:call-template name="Product" />  
        </xsl:for-each>
      </Products>
    </Company>
  </xsl:template>

  <xsl:template name="Product">
    <Product>
      <Id><xsl:value-of select="id"/></Id>
      <Sku><xsl:value-of select="sku"/></Sku>
      <Name><xsl:value-of select="name"/></Name>
      <LongDescription>
        <xsl:text disable-output-escaping="yes"><![CDATA[</xsl:text>
        <xsl:value-of select="description" disable-output-escaping="yes"/>
        <xsl:text disable-output-escaping="yes">]]></xsl:text>
      </LongDescription>

      <xsl:choose>
        <xsl:when test="images/image[1]/is_thumbnail = 'true'">
          <ThumbnailUrl><xsl:value-of select="images/image[1]/image_file"/></ThumbnailUrl>
        </xsl:when>
        <xsl:when test="images/image[1]/is_thumbnail = 'false'">
          <ImageUrl><xsl:value-of select="images/image[1]/image_file"/></ImageUrl>
        </xsl:when>
      </xsl:choose>

      <QtyInStock><xsl:value-of select="inventory_level" /></QtyInStock>
      <SalePrice><xsl:value-of select="price"/></SalePrice>
      <UnitWeight><xsl:value-of select="weight"/></UnitWeight>
      <Publish><xsl:value-of select="is_visible"/></Publish>
      <ImageName><xsl:value-of select="images/image[1]/image_file"/></ImageName>

      <DateModified>
        <xsl:call-template name="formatDate">
          <xsl:with-param name="dateTimeStr" select="date_modified" />
        </xsl:call-template>
      </DateModified>

      <Dimensions>
        <Dimension>
          <Id>1</Id>
          <Name>Width</Name>
          <Value><xsl:value-of select="width"/></Value>
        </Dimension>
        <Dimension>
          <Id>2</Id>
          <Name>Height</Name>
          <Value><xsl:value-of select="height"/></Value>
        </Dimension>
        <Dimension>
          <Id>3</Id>
          <Name>Depth</Name>
          <Value><xsl:value-of select="depth"/></Value>
        </Dimension>
      </Dimensions>

      <Manufacturer><xsl:value-of select="brand/id"/></Manufacturer>
      <xsl:if test="type = 'physical'">
        <ItemType>Stock</ItemType>
      </xsl:if>
    </Product>
  </xsl:template>

  <!-- Converts a date to the correct format -->
  <xsl:template name="formatDate">
    <xsl:param name="dateTimeStr" />
    <xsl:variable name="dateTime" select="substring-after(substring-before($dateTimeStr, ' +'), ', ')" />
    <xsl:variable name="date" select="substring($dateTime,0,12)"/>
    <xsl:variable name="time" select="substring($dateTime,13)"/>

    <xsl:variable name="day" select="substring-before($date, ' ')"/>
    <xsl:variable name="monthStr" select="substring-before(substring-after($date, ' '), ' ')"/>
    <xsl:variable name="year" select="substring-after(substring-after($date, ' '), ' ')"/>

    <xsl:choose>
      <xsl:when test="$monthStr = 'Jan'">
        <xsl:value-of select="concat($year, '-01-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Feb'">
        <xsl:value-of select="concat($year, '-02-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Mar'">
        <xsl:value-of select="concat($year, '-03-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Apr'">
        <xsl:value-of select="concat($year, '-04-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'May'">
        <xsl:value-of select="concat($year, '-05-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Jun'">
        <xsl:value-of select="concat($year, '-06-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Jul'">
        <xsl:value-of select="concat($year, '-07-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Aug'">
        <xsl:value-of select="concat($year, '-08-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Sep'">
        <xsl:value-of select="concat($year, '-09-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Oct'">
        <xsl:value-of select="concat($year, '-10-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Nov'">
        <xsl:value-of select="concat($year, '-11-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Dec'">
        <xsl:value-of select="concat($year, '-12-', $day, 'T', $time)" />
      </xsl:when>
    </xsl:choose>
  </xsl:template>
</xsl:stylesheet>
```