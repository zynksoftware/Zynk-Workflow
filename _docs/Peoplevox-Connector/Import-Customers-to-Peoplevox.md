---
slug: import-customers-to-peoplevox
title: Import Customers to Peoplevox
---

This task will import customer information to Peoplevox in XML format, for detailed information see [Peoplevox Customer XML](peoplevox-customer-xml).  The information is imported using the standard fields under Integration Templates that can be configured through your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Integration Templates
### Customer
[Download Template](/assets/resources/peoplevox/customer.csv)

```csv
Name,Reference,FirstName,LastName,Phone,Mobile,Email,CreditLimit,CreditStatus,Wholesaler
```

### Customer Address
[Download Template](/assets/resources/peoplevox/customer_address.csv)

```csv
CustomerReference,AddressLine1,AddressLine2,AddressCity,AddressRegion,AddressPostcode,AddressCountry,AddressReference
```

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### Input File
_Required_  
The name or full path to the file the data to be imported will be read from.  Defaults to `peoplevox_import_customers.xml`, which should exist in the working directory of the Workflow.

### Success File
_Required_  
The name or full path to the file successfully imported records will be saved to.  Defaults to `peoplevox_import_customers_success.xml`, which will be created in the working directory of the Workflow.

### Fail File
_Required_  
The name or full path to the file falied records will be saved to.  Defaults to `peoplevox_import_customers_fail.xml`, which will be created in the working directory of the Workflow.

### Prevent Reprocessing
_Required_  
Set to true if you only want to process a record once, or false to update every time.  Defaults to False.

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

## Example XML
Example input file, for detailed information see [Peoplevox Customer XML](peoplevox-customer-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers>
	<Customer>
		<Name>Andrew Snape</Name>
		<Reference>ANDR001</Reference>
		<FirstName>Andrew</FirstName>
		<LastName>Snape</LastName>
		<Phone>0191 303 7279</Phone>
		<Mobile>0191 303 7279</Mobile>
		<Email>support@zynk.com</Email>
		<CreditLimit>1000</CreditLimit>
		<CreditStatus>true</CreditStatus>
		<Wholesaler>false</Wholesaler>
		<CustomerAddresses>
			<CustomerAddress>
				<AddressLine1>i6</AddressLine1>
				<AddressLine2>6 - 8 Charlotte Square</AddressLine2>
				<AddressCity>Newcastle</AddressCity>
				<AddressRegion>Tyne and Wear</AddressRegion>
				<AddressPostcode>NE1 4XF</AddressPostcode>
				<AddressCountry>United Kingdom</AddressCountry>
				<AddressReference>WORK</AddressReference>
			</CustomerAddress>
		</CustomerAddresses>
	</Customer>
</Customers>
```