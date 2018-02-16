---
slug: downloading-customers-from-corecommerce
redirect_from: "/article/187-downloading-customers-from-corecommerce"
title: Downloading Customers from CoreCommerce
---
This task will import download customers from CoreCommerce in the CoreCommerce XML format.

## Settings
### Connection
_Required_  
The CoreCommerce connection to use. See the [Connecting to CoreCommerce](connecting-to-corecommerce) article if you require more information on how to create/manage connections.

### Customer IDs
_Optional_  
Enter a list of specific customer IDs to download. The list can be entered as either a comma separated list, or using the 'Use a list' option on the  Zynk Object form.

### Customer Strings
_Optional_  
Enter a list of specific customer strings to download. The list can be entered as either a comma separated list, or using the 'Use a list' option on the  Zynk Object form.

### Emails
_Optional_  
Enter a list of specific email addresses to download. The list can be entered as either a comma separated list, or using the 'Use a list' option on the  Zynk Object form.

### Output File
_Required_  
The file to save the downloaded customers to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [Core Commerce to Sage 50 Integration](core-commerce-to-sage-50-integration) article.

Sample output file:
```xml
<?xml version="1.0"?>
<Response xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Action>ACTION_TYPE_CUSTOMER_LIST</Action>
	<Status>SUCCESS_CODE</Status>
	<Code />
	<List length="1" possibleLength="1">
		<Customer id="5609">
			<CustomerString>8c4eeacb8991dc88964052302a0ca251</CustomerString>
			<BillingSameAsShipping>FALSE_VALUE</BillingSameAsShipping>
			<Address>
				<FirstName>Adam</FirstName>
				<LastName>W</LastName>
				<Address1>Flemming Business Centre</Address1>
				<Address2>Jesmond</Address2>
				<City>Newcastle</City>
				<State />
				<Zip>NE2 3AE</Zip>
				<Email>support@zynk.com</Email>
				<Company>Zynk</Company>
				<County />
				<Country>GB</Country>
			</Address>
			<ShippingAddress>
				<FirstName>Adam</FirstName>
				<LastName>W</LastName>
				<Address1>Flemming Business Centre</Address1>
				<Address2>Jesmond</Address2>
				<City>Newcastle</City>
				<State />
				<Zip>NE2 3AE</Zip>
				<Email>support@zynk.com</Email>
				<Company>Zynk</Company>
				<County />
				<Country>GB</Country>
			</ShippingAddress>
			<CustomerGroupId>5</CustomerGroupId>
			<Phone>01969 623497</Phone>
			<Fax />
			<InternalNumber>ADA001</InternalNumber>
			<HowHeardAbout>Customer</HowHeardAbout>
			<Password>abc123</Password>
			<PasswordHint />
			<Memo>AUTHORISED</Memo>
			<LastUpdated>
				<UnixTimeStamp>1410967275</UnixTimeStamp>
				<Day>17</Day>
				<Month>09</Month>
				<Year>2014</Year>
				<Hour>10</Hour>
				<Minute>21</Minute>
				<Second>15</Second>
			</LastUpdated>
			<TaxExempt>FALSE_VALUE</TaxExempt>
			<FreeShipping>FALSE_VALUE</FreeShipping>
			<StoneEdgeExported>FALSE_VALUE</StoneEdgeExported>
			<CustomFields length="0" />
			<Status />
		</Customer>
	</List>
</Response>
```