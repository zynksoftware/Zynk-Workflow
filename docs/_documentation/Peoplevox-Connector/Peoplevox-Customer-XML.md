---
slug: peoplevox-customer-xml
title: Peoplevox Customer XML
---

Zynk will import the data using the standard fields under Integration Templates that can be ran configured your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Tasks

 * [Import Customers to Peoplevox](import-customers-to-peoplevox)

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

## Identifiers
For inserting or updating records to Peoplevox Zynk uses the Reference field on a Customer, and AddressReference on a CustomerAddress.  It is invalid to insert / update a Customer without providing the Reference.  If an AddressReference is not provided a new address will be created.

## Fields
### Reference
_Required_  
External reference.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | ZYNK001 | `<Reference>ZYNK001</Reference>` |

### Name
_Required_  
Name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Zynk Software Ltd. | `<Name>Zynk Software Ltd.</Name>` |

### FirstName
_Optional_  
First name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Andrew | `<FirstName>Andrew</FirstName>` |

### LastName
_Optional_  
Last name.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | Snape | `<LastName>Snape</LastName>` |

### Phone
_Optional_  
Phone number.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | 0191 303 7279 | `<Phone>0191 303 7279</Phone>` |

### Mobile
_Optional_  
Mobile number.

| Type | Example | XML |
| --- | --- | --- |
| string(50) | 0191 303 7279 | `<Mobile>0191 303 7279</Mobile>` |

### Email
_Optional_  
Email address.

| Type | Example | XML |
| --- | --- | --- |
| string(500) | support@zynk.com | `<Email>support@zynk.com</Email>` |

### CreditLimit
_Optional_  
Credit limit.

| Type | Example | XML |
| --- | --- | --- |
| decimal | 1000 | `<CreditLimit>1000</CreditLimit>` |

### CreditStatus
_Optional_  
Credit status, false by default.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<CreditStatus>true</CreditStatus>` |

#### Available Values
 * true
 * false

### Wholesaler
_Optional_  
Wholesaler flag, false by default.

| Type | Example | XML |
| --- | --- | --- |
| boolean | false | `<Wholesaler>false</Wholesaler>` |

#### Available Values
 * true
 * false

### CustomerAddresses
_Optional_  
You can provide a collection of addresses as part of the import.

#### AddressReference
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string(100) | WORK | `<AddressReference>WORK</AddressReference>` |

#### AddressLine1
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string(100) | i6 | `<AddressLine1>i6</AddressLine1>` |

#### AddressLine2
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string(100) | 6 - 8 Charlotte Square | `<AddressLine2>6 - 8 Charlotte Square</AddressLine2>` |

#### AddressCity
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Newcastle | `<AddressCity>Newcastle</AddressCity>` |

#### AddressRegion
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string(100) | Tyne and Wear | `<AddressRegion>Tyne and Wear</AddressRegion>` |

#### AddressPostcode
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string(100) | NE1 4XF | `<AddressPostcode>NE1 4XF</AddressPostcode>` |

#### AddressCountry
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string(100) | United Kingdom | `<AddressCountry>United Kingdom</AddressCountry>` |

## Example XML

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