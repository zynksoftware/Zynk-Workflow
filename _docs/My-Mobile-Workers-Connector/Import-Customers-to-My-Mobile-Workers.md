---
slug: import-customers-to-my-mobile-workers
title: Import Customers to My Mobile Workers
---
The My Mobile Workers platform will allow you to import customers via the API. For example, if you have customer records that are maintained in an external system that you want to keep up to date in My Mobile Workers you would use this task as part of your process to import them.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Add_Customer).

This task will import customers to My Mobile Workers in an XML format.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

### Fail File
_Required_
The file to write failed records to.

### Input File
_Required_
The file containing the records you wish to process.

### Success File
_Required_
The file to write successful records to.

## XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData>
	<Customers>
		<Customer>
			<name>Test Company</name>
			<external_id>000001</external_id>
			<contact_name>Test Person</contact_name>
			<address_1>123 Test Road</address_1>
			<address_3>Newcastle</address_3>
			<address_4>Tyne and Wear</address_4>
			<postcode>NE1 4XF</postcode>
			<contact_number>01913037279</contact_number>
		</Customer>
	</Customers>
</MyMobileWorkersData>
```
