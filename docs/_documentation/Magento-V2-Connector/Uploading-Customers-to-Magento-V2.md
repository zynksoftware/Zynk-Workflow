---
slug: uploading-customers-to-magento-v2
redirect_from: "/article/772-uploading-customers-to-magento"
title: Uploading Customers to Magento V2
---
This task will create or update customers in Magento. See below for a sample input file.

If the `<id>` element is specified in the input file, the task will update the customer with the specified ID. If no ID is specified, the task will use the `<email>` element to check if the customer already exists. If a match is found the existing customer will be updated, otherwise a new customer will be created.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

## Fail File
_Required_  
The XML file to save failed customer uploads to. The data will be written in the same format as the input file.

## Input File
_Required_  
The XML file containing the customers to upload in Magento.

## Success File
_Required_  
The XML file to save successful customer uploads to. The data will be written in the same format as the input file.

## Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. This will create or update the customer with the email address `support@zynk.com`.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <external_id>WARD0001</external_id>
    <group_id>1</group_id>
    <dob xsi:nil="true" />
    <email>support@zynk.com</email>
    <firstname>Adam</firstname>
    <lastname>Wardle</lastname>
    <gender>0</gender>
    <store_id>1</store_id>
    <website_id>1</website_id>
    <addresses>
      <address>
        <region>
          <region>Tyne &amp; Wear</region>
        </region>
        <country_id>GB</country_id>
        <street>
          <string>Nelson House</string>
          <string>Jesmond</string>
        </street>
        <telephone>214153215</telephone>
        <postcode>NE2 3AE</postcode>
        <city>Newcastle</city>
        <firstname>Adam</firstname>
        <lastname>Wardle</lastname>
        <default_billing>true</default_billing>
        <default_shipping>true</default_shipping>
      </address>
    </addresses>
  </Customer>
</ArrayOfCustomer>
```

Sample XSLT file to use to transform customers exported from Sage in the Zynk XML Customers format, to the Magento customer format. This is also available in the [Auto Mapper](auto-mapper).
```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">

    <xsl:output method="xml" indent="yes"/>

    <xsl:template match="/">
        <ArrayOfCustomer>
            <xsl:for-each select="Company/Customers/Customer">
                <xsl:call-template name="Customer" />
            </xsl:for-each>
        </ArrayOfCustomer>
    </xsl:template>

    <xsl:template name="Customer">
        <Customer>
            <xsl:if test="Id">
              <id><xsl:value-of select="Id" /></id>
            </xsl:if>
            <external_id><xsl:value-of select="AccountReference" /></external_id>
            <suffix><xsl:value-of select="AccountReference" /></suffix>
            <firstname><xsl:value-of select="CustomerInvoiceAddress/Forename" /></firstname>
            <lastname><xsl:value-of select="CustomerInvoiceAddress/Surname" /></lastname>
            <email><xsl:value-of select="CustomerInvoiceAddress/Email" /></email>
            <addresses>
              <address>
                <xsl:if test="Id">
                  <customer_id><xsl:value-of select="UniqueId"/></customer_id>
                </xsl:if>
                <firstname><xsl:value-of select="CustomerInvoiceAddress/Forename" /></firstname>
                <lastname><xsl:value-of select="CustomerInvoiceAddress/Surname" /></lastname>
                <street>
                  <string><xsl:value-of select="CustomerInvoiceAddress/Address1"/></string>
                  <string><xsl:value-of select="CustomerInvoiceAddress/Address2"/></string>
                </street>
                <city><xsl:value-of select="CustomerInvoiceAddress/Town" /></city>
                <region>
                  <region><xsl:value-of select="CustomerInvoiceAddress/County" /></region>
                </region>    
                <postcode><xsl:value-of select="CustomerInvoiceAddress/Postcode" /></postcode>
                <country_id><xsl:value-of select="CustomerInvoiceAddress/Country" /></country_id>
                <telephone><xsl:value-of select="CustomerInvoiceAddress/Telephone" /></telephone>
                <default_billing>true</default_billing>
                <default_shipping>true</default_shipping>
              </address>
            </addresses>
        </Customer>
    </xsl:template>

</xsl:stylesheet>
```
