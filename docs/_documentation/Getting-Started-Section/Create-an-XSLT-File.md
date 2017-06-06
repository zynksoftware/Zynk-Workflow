---
slug: create-an-xslt-file
redirect_from: "/article/621-create-an-xslt-file"
title: Create an XSLT File
---
Let's say you have an XML file which looks like this:-

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
	<Row Id="1" Name="DataMining Ltd" />
	<Row Id="2" Name="Nelson Inc" />
	<Row Id="3" Name="Internetware Ltd" />
</Rows>
```

If you want to transform this data into a format that can be used by the Sage 50 Connect module, you would use an XSLT transformer            which is a simple text file containing instructions on how to convert the XML

All the XSLT processing instructions start with the prefix XSL followed by an instruction e.g. `<xsl:value-of select="Variable" />`

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0"xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
	<xsl:template match="/">
		<Company>
			<Customers>
				<xsl:for-each select="Rows/Row">
					<Customer>
						<AccountRef>
							<xsl:value-of select= "Id"/>
						</AccountRef>
						<Name>
							<xsl:value-of select= "Name"/>
						</Name>
					</Customer>
				</xsl:for-each>
			</Customers>
		</Company>
	</xsl:template>
</xsl:stylesheet>
```

Output from XSL transform           

```xml
<?xml version= "1.0" standalone= "yes"?>
<Company>
	<Customers>
		<Customer>
			<AccountRef>DataMining Ltd</AccountRef>
			<Name>DataMining Ltd</Name>
		</Customer>
		<Customer>
			<AccountRef>2</AccountRef>
			<Name>Nelson Inc</Name>
		</Customer>
		<Customer>
			<AccountRef>3</AccountRef>
			<Name>Internetware Ltd</Name>
		</Customer>
	</Customers>
</Company>
```