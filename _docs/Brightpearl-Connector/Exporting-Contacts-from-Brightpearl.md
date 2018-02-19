---
slug: exporting-contacts-from-brightpearl
redirect_from: "/article/174-downloading-contacts-from-brightpearl"
title: Exporting Contacts from Brightpearl
---


This task will download contacts from Brightpearl in XML format.


## Settings

### Connection
_Required_
The Brightpearl connection to use. See the [Connecting to Brightpearl](connecting-to-brightpearl)

### Contact Type
_Required_
Select the type of contacts to export from Brightpearl. The available options are:	  

- Any - All types of contact will be downloaded
- Customers - Only customer contacts will be downloaded
- Suppliers - Only supplier contacts will be downloaded
- Staff - Only staff contacts will be downloaded

### Brightpearl Settings
See [Common Brightpearl Settings](common-brightpearl-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample output file:


```xml
<?xml version="1.0"?>
<ArrayOfContact>
	<Contact>
		<externalId />
		<createdOn>2010-08-17T13:57:14+01:00</createdOn>
		<updatedOn>2016-11-24T10:11:22Z</updatedOn>
		<contactId>200</contactId>
		<isPrimaryContact>true</isPrimaryContact>
		<salutation>Mr.</salutation>
		<firstName>Demo</firstName>
		<lastName>Customer</lastName>
		<postalAddresses>
			<defaultAddress>
				<addressId>107</addressId>
				<addressLine1>34 Lime St</addressLine1>
				<addressLine2>Barton</addressLine2>
				<addressLine3>Sheffield</addressLine3>
				<addressLine4>South Yorkshire</addressLine4>
				<postalCode>S1 4RT</postalCode>
				<countryIsoCode>GBR</countryIsoCode>
				<countryId>222</countryId>
			</defaultAddress>
			<billingAddress>
				<addressId>107</addressId>
				<addressLine1>34 Lime St</addressLine1>
				<addressLine2>Barton</addressLine2>
				<addressLine3>Sheffield</addressLine3>
				<addressLine4>South Yorkshire</addressLine4>
				<postalCode>S1 4RT</postalCode>
				<countryIsoCode>GBR</countryIsoCode>
				<countryId>222</countryId>
			</billingAddress>
			<deliveryAddress>
				<addressId>107</addressId>
				<addressLine1>34 Lime St</addressLine1>
				<addressLine2>Barton</addressLine2>
				<addressLine3>Sheffield</addressLine3>
				<addressLine4>South Yorkshire</addressLine4>
				<postalCode>S1 4RT</postalCode>
				<countryIsoCode>GBR</countryIsoCode>
				<countryId>222</countryId>
			</deliveryAddress>
		</postalAddresses>
		<communication>
			<emails>
				<PRI>
					<email>demo@test.com</email>
				</PRI>
			</emails>
			<telephones>
				<PRI>01245 845632</PRI>
			</telephones>
			<messagingVoips />
			<websites />
		</communication>
		<contactStatus>
			<current>
				<contactStatusId>0</contactStatusId>
			</current>
		</contactStatus>
		<relationshipToAccount>
			<isSupplier>false</isSupplier>
			<isStaff>false</isStaff>
		</relationshipToAccount>
		<marketingDetails>
			<isReceiveEmailNewsletterStaff xsi:nil="true" />
		</marketingDetails>
		<financialDetails>
			<priceList>
				<id>1</id>
				<name>
					<languageCode>en</languageCode>
					<text>Cost</text>
					<format>PLAINTEXT</format>
				</name>
				<code>COST</code>
				<currencyCode>GBP</currencyCode>
				<currencySymbol>£</currencySymbol>
				<currencyId>1</currencyId>
				<priceListTypeCode>BUY</priceListTypeCode>
				<gross>false</gross>
			</priceList>
			<nominalCode>0</nominalCode>
			<creditLimit>1000</creditLimit>
			<creditTermDays>30</creditTermDays>
			<currency>
				<id>1</id>
				<title>British Pound Sterling</title>
				<code>GBP</code>
				<symbol>£</symbol>
				<exchangeRate>1.000000</exchangeRate>
				<isDefault>true</isDefault>
			</currency>
			<discountPercentage>0</discountPercentage>
		</financialDetails>
		<assignment>
			<current>
				<staffOwnerContactId xsi:nil="true" />
				<departmentId xsi:nil="true" />
				<leadSourceId xsi:nil="true" />
				<channelId xsi:nil="true" />
				<projectId xsi:nil="true" />
			</current>
		</assignment>
		<organisation>
			<organisationId xsi:nil="true" />
			<name>Customer Company Ltd.</name>
		</organisation>
		<createdByid>2</createdByid>
		<contactTags>1</contactTags>
		<customFields />
	</Contact>
</ArrayOfContact>
```

