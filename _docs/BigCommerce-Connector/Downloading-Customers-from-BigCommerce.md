---
slug: downloading-customers-from-bigcommerce
redirect_from: "/article/167-downloading-customers-from-bigcommerce"
title: Downloading Customers from BigCommerce
---
This task will download customers registered on your BigCommerce store to an XML file.

## Settings
### Connection
_Required_  
The BigCommerce connection to use. See the Connecting to BigCommerce article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set this option to true to download all customers from your store, or set to false to download only new or modified customers since this task last ran. Defaults to False.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. customers.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below showing the customer 'Zynk Software Limited'.

```xml
<?xml version="1.0" encoding="utf-8"?>
<customers>
	<customer>
		<id>1</id>
		<company>Zynk Software Limited</company>
		<first_name>Joe</first_name>
		<last_name>Harrison</last_name>
		<email>support@zynk.com</email>
		<phone>0845 123 2920</phone>
		<date_created>Fri, 09 Aug 2013 13:04:01 +0000</date_created>
		<date_modified>Fri, 09 Aug 2013 13:04:01 +0000</date_modified>
		<store_credit>0.0000</store_credit>
		<registration_ip_address>XXX.XXX.XXX.XXX</registration_ip_address>
		<customer_group_id>0</customer_group_id>
		<notes/>
		<addresses>
			<address>
				<id>1</id>
				<customer_id>1</customer_id>
				<first_name>Joe</first_name>
				<last_name>Harrison</last_name>
				<company>Zynk Software Limited</company>
				<street_1>6-8 Charlotte Square</street_1>
				<street_2>i6</street_2>
				<city>Newcastle upon-Tyne</city>
				<state>Tyne and Wear</state>
				<zip>NE1 4XF</zip>
				<country>United Kingdom</country>
				<country_iso2>GB</country_iso2>
				<phone>0845 123 2920</phone>
			</address>
		</addresses>
	</customer>
</customers>
```

A sample XSLT file is shown below to transform the output file from this task to the Zynk XML Customers format, ready for import into Sage. This is also available in the [Auto Mapper](auto-mapper).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">
	<xsl:output method="xml" indent="yes" />
	<xsl:param name="AccountReference" />
	<xsl:param name="NominalCode" />
	<xsl:template match="/">
		<Company>
			<Customers>
				<xsl:for-each select="customers/customer">
					<xsl:call-template name="Customer" />
				</xsl:for-each>
			</Customers>
		</Company>
	</xsl:template>
	<xsl:template name="Customer">
		<Customer>
			<Id><xsl:value-of select="id" /></Id>
			<CompanyName><xsl:value-of select="company" /></CompanyName>
			<AccountReference><xsl:value-of select="$AccountReference" /></AccountReference>
			<CustomerInvoiceAddress>
				<Forename><xsl:value-of select="addresses/address[1]/first_name" /></Forename>
				<Surname><xsl:value-of select="addresses/address[1]/last_name" /></Surname>
				<Company><xsl:value-of select="addresses/address[1]/company" /></Company>
				<Address1><xsl:value-of select="addresses/address[1]/street_1" /></Address1>
				<Address2><xsl:value-of select="addresses/address[1]/street_2" /></Address2>
				<Town><xsl:value-of select="addresses/address[1]/city" /></Town>
				<Postcode><xsl:value-of select="addresses/address[1]/zip" /></Postcode>
				<County><xsl:value-of select="addresses/address[1]/state" /></County>
				<Country><xsl:value-of select="addresses/address[1]/country" /></Country>
				<Telephone><xsl:value-of select="addresses/address[1]/phone" /></Telephone>
				<Email><xsl:value-of select="email" /></Email>
			</CustomerInvoiceAddress>
			<Memo><xsl:value-of select="notes" /></Memo>
			<NominalCode><xsl:value-of select="$NominalCode" /></NominalCode>
			<CustomFields>
				<CustomField>
					<Name>date_created</Name>
					<Value>
						<xsl:call-template name="formatDate">
							<xsl:with-param name="dateTimeStr" select="date_created" />
						</xsl:call-template>
					</Value>
				</CustomField>
				<CustomField>
					<Name>date_modified</Name>
					<Value>
						<xsl:call-template name="formatDate">
							<xsl:with-param name="dateTimeStr" select="date_modified" />
						</xsl:call-template>
					</Value>
				</CustomField>
				<CustomField>
					<Name>store_credit</Name>
					<Value>
						<xsl:value-of select="store_credit" />
					</Value>
				</CustomField>
				<CustomField>
					<Name>customer_group_id</Name>
					<Value>
						<xsl:value-of select="customer_group_id" />
					</Value>
				</CustomField>
			</CustomFields>
		</Customer>
	</xsl:template>

	<!-- Converts a date to the correct format -->
	<xsl:template name="formatDate">
		<xsl:param name="dateTimeStr" />
		<xsl:variable name="dateTime" select="substring-after(substring-before($dateTimeStr, ' +'), ', ')" />
		<xsl:variable name="date" select="substring($dateTime,0,12)" />
		<xsl:variable name="time" select="substring($dateTime,13)" />
		<xsl:variable name="day" select="substring-before($date, ' ')" />
		<xsl:variable name="monthStr" select="substring-before(substring-after($date, ' '), ' ')" />
		<xsl:variable name="year" select="substring-after(substring-after($date, ' '), ' ')" />
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