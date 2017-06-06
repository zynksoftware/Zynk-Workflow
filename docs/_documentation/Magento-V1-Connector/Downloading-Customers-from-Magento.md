---
slug: downloading-customers-from-magento
redirect_from: "/article/260-downloading-customers-from-magento"
title: Downloading Customers from Magento
---
This task will download customer information from Magento in XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Download Address Book
_Required_  
Set to true to download the full list of addresses for each customer.

### Download All
_Required_  
Set to true to download all customers matching the filter, set to false to only download new/modified customers matching the filter.

### Download Detailed
_Required_  
Set to true to download billing and shipping addresses, set to false to only download basic information.

### Download From
_Required_  
The rolling date to download new/modified customers from, when Download All is set to true. This will update automatically each time the task runs.

### Start Date
_Optional_  
Any customers created before this date will be ignored, even if modified.

### Output File
_Required_  
The name of the file to export the customers to.

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
<ArrayOfCustomer>
  <Customer>
    <firstname>Andrew</firstname>
    <updated_at>2012-01-13 11:03:34</updated_at>
    <group_id>1</group_id>
    <suffix />
    <customer_id>1</customer_id>
    <default_billing>9</default_billing>
    <prefix>Mr</prefix>
    <store_id>0</store_id>
    <lastname>Snape</lastname>
    <password_hash>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx:XX</password_hash>
    <default_shipping>9</default_shipping>
    <website_id>1</website_id>
    <middlename />
    <created_at>2011-10-14 00:00:00</created_at>
    <email>support@zynk.com</email>
    <default_billing_address>
      <city>Newcastle</city>
      <firstname>Andrew</firstname>
      <updated_at>2012-01-13 11:03:34</updated_at>
      <is_default_shipping>true</is_default_shipping>
      <country_id>GB</country_id>
      <company>Internetware</company>
      <postcode>NE1 4XF</postcode>
      <prefix>Mr</prefix>
      <region>Tyne and Wear</region>
      <lastname>Snape</lastname>
      <is_default_billing>true</is_default_billing>
      <fax>0845 123 2921</fax>
      <street>Newcastle Business Centre
6 Charlotte Square</street>
      <middlename />
      <telephone>0845 123 2920</telephone>
      <created_at>2012-01-13 09:49:18</created_at>
      <region_id>0</region_id>
    </default_billing_address>
    <default_shipping_address>
      <city>Newcastle</city>
      <firstname>Andrew</firstname>
      <updated_at>2012-01-13 11:03:34</updated_at>
      <is_default_shipping>true</is_default_shipping>
      <country_id>GB</country_id>
      <company>Internetware</company>
      <postcode>NE1 4XF</postcode>
      <prefix>Mr</prefix>
      <region>Tyne and Wear</region>
      <lastname>Snape</lastname>
      <is_default_billing>true</is_default_billing>
      <fax>0845 123 2921</fax>
      <street>Newcastle Business Centre
6 Charlotte Square</street>
      <middlename />
      <telephone>0845 123 2920</telephone>
      <created_at>2012-01-13 09:49:18</created_at>
      <region_id>0</region_id>
    </default_shipping_address>
  </Customer>
</ArrayOfCustomer>
```

Sample XSLT file for transforming the Magento XML customers to Zynk XML customers (also available in the [Auto Mapper](auto-mapper))
```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0"
xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

    <xsl:output
    method="xml"
    omit-xml-declaration="no"
    standalone="yes"
    indent="yes"/>

    <xsl:template match="/">
        <Company>
            <Customers>
                <xsl:for-each select="ArrayOfCustomer/Customer">
                    <xsl:call-template name="Customer" />
                </xsl:for-each>
            </Customers>
        </Company>
    </xsl:template>

    <xsl:template name="Customer">
        <Customer>
            <Id><xsl:value-of select="email"/></Id>
            <CompanyName><xsl:value-of select="default_billing_address/company"/></CompanyName>
            <CustomerInvoiceAddress>
                <Title><xsl:value-of select="default_billing_address/prefix"/></Title>
                <Forename><xsl:value-of select="default_billing_address/firstname"/></Forename>
                <Middlename><xsl:value-of select="default_billing_address/middlename"/></Middlename>
                <Surname><xsl:value-of select="default_billing_address/lastname"/></Surname>
                <Company><xsl:value-of select="default_billing_address/company"/></Company>
                <Address1><xsl:value-of select="default_billing_address/street"/></Address1>
                <Town><xsl:value-of select="default_billing_address/city"/></Town>
                <Postcode><xsl:value-of select="default_billing_address/postcode"/></Postcode>
                <County><xsl:value-of select="default_billing_address/region"/></County>
                <Country><xsl:value-of select="default_billing_address/country_id"/></Country>
                <Telephone><xsl:value-of select="default_billing_address/telephone"/></Telephone>
                <Fax><xsl:value-of select="default_billing_address/fax"/></Fax>
                <Email><xsl:value-of select="email"/></Email>
            </CustomerInvoiceAddress>
            <CustomerDeliveryAddress>
                <Title><xsl:value-of select="default_shipping_address/prefix"/></Title>
                <Forename><xsl:value-of select="default_shipping_address/firstname"/></Forename>
                <Middlename><xsl:value-of select="default_shipping_address/middlename"/></Middlename>
                <Surname><xsl:value-of select="default_shipping_address/lastname"/></Surname>
                <Company><xsl:value-of select="default_shipping_address/company"/></Company>
                <Address1><xsl:value-of select="default_shipping_address/street"/></Address1>
                <Town><xsl:value-of select="default_shipping_address/city"/></Town>
                <Postcode><xsl:value-of select="default_shipping_address/postcode"/></Postcode>
                <County><xsl:value-of select="default_shipping_address/region"/></County>
                <Country><xsl:value-of select="default_shipping_address/country_id"/></Country>
                <Telephone><xsl:value-of select="default_shipping_address/telephone"/></Telephone>
                <Fax><xsl:value-of select="default_shipping_address/fax"/></Fax>
                <Email><xsl:value-of select="email"/></Email>
            </CustomerDeliveryAddress>
            <TermsAgreed>1</TermsAgreed>
            <AccountStatus>1</AccountStatus>
        </Customer>
    </xsl:template>
```