---
slug: downloading-products-from-magento
redirect_from: "/article/263-downloading-products-from-magento"
title: Downloading Products from Magento
---
This task will download product details from Magento in XML format. The results can be filtered if required.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all products, set to false to download only those products which have been modified since the last time the task was run.

### Download Detailed
_Required_  
Set to true to download detailed information for each product, set to false to download only basic information.

### Download From
_Required_  
The rolling date to download new/modified products from, when Download All is set to false. Will update automatically each time the task runs.

### Start Date
_Optional_  
No products created before this date will be downloaded, even if they are modified.

### Output File
_Required_  
The name of the file to export the products to.

### Filter Property
_Optional_  
The property the filter is to be based upon. The property name should match the API field name, as seen in the output file.

### Filter Type
_Optional_  
The following types of filter are available:

* __eq__ - Returns records where the property matches the specified value
* __gt__ - Returns records where the property is greater than the specified value
* __lt__ - Returns records where the property is less than the specified value.
* __like__ - Returns records where the property contains the specified value.
* __isnull__ - Returns records where the property is null.
* __notnull__ - Returns records where the property is not null.

### Filter Value
_Optional_  
The value the filter is to be based upon. When using the eq filter type, you can specify multiple values by separating them with commas, or using the 'Use a list' option after clicking the ellipsis (...) button.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0"?>
<ArrayOfProduct>
  <Product>
    <Fields>
      <Field Name="country_of_manufacture" Value="" />
      <Field Name="msrp_enabled" Value="2" />
      <Field Name="msrp_display_actual_price_type" Value="4" />
      <Field Name="msrp" Value="" />
      <Field Name="is_recurring" Value="0" />
      <Field Name="recurring_profile" Value="" />
      <Field Name="page_layout" Value="" />
    </Fields>
    <type>simple</type>
    <created_at>2014-01-17 14:00:25</created_at>
    <status>1</status>
    <options_container>container2</options_container>
    <category_ids />
    <description>test</description>
    <tier_price />
    <visibility>4</visibility>
    <short_description>test</short_description>
    <required_options>0</required_options>
    <url_key>test</url_key>
    <updated_at>2014-01-17 14:00:25</updated_at>
    <websites>
      <string>1</string>
    </websites>
    <url_path>test.html</url_path>
    <has_options>0</has_options>
    <product_id>1</product_id>
    <tax_class_id>2</tax_class_id>
    <type_id>simple</type_id>
    <set>4</set>
    <categories />
    <enable_googlecheckout>1</enable_googlecheckout>
    <sku>PROD001</sku>
    <name>test</name>
    <weight>2.0000</weight>
    <price>10.0000</price>
    <group_price />
  </Product>
</ArrayOfProduct>
```

Sample XSLT file to use to transform the output file from this task to the Zynk XML Products format, ready for import into Sage. This is also available in the [Auto Mapper](auto-mapper).
```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="xml" standalone="yes" indent="yes"/>

  <xsl:template match="/">
    <Company>
      <Products>
        <xsl:for-each select="ArrayOfProduct/Product">
          <xsl:call-template name="Product" />
        </xsl:for-each>
      </Products>
    </Company>
  </xsl:template>

  <xsl:template name="Product">
    <!-- Only add products that have a price -->
    <xsl:choose>
      <xsl:when test="price > 0">
        <Product>
          <Sku><xsl:value-of select="sku"/></Sku>
          <Name><xsl:value-of select="name"/></Name>
          <Description><xsl:value-of select="description"/></Description>
          <SalePrice><xsl:value-of select="price"/></SalePrice>
          <UnitWeight><xsl:value-of select="weight"/></UnitWeight>
        </Product>
      </xsl:when>
      <xsl:otherwise><!-- Do nothing --></xsl:otherwise>
    </xsl:choose>
  </xsl:template>

</xsl:stylesheet>
```