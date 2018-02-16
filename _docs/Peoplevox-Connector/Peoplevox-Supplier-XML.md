---
slug: peoplevox-supplier-xml
title: Peoplevox Supplier XML
---

Zynk will import the data using the standard fields under Integration Templates that can be ran configured your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Tasks

 * [Import Suppliers to Peoplevox](import-suppliers-to-peoplevox)

## Integration Templates
### Supplier
[Download Template](/assets/resources/peoplevox/supplier.csv)

```csv
Name,Reference,FirstName,LastName,Phone,Mobile,Email,CreditLimit,Notes
```

### Supplier Address
[Download Template](/assets/resources/peoplevox/supplier_address.csv)

```csv
SupplierReference,AddressLine1,AddressLine2,AddressCity,AddressRegion,AddressPostcode,AddressCountry,AddressReference
```

## Identifiers
For inserting or updating records to Peoplevox Zynk uses the Reference field on a Supplier, and AddressReference on a SupplierAddress.  It is invalid to insert / update a Supplier without providing the Reference.  If an AddressReference is not provided a new address will be created.

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

### Notes
_Optional_  
Notes.

| Type | Example | XML |
| --- | --- | --- |
| string(1000) | Main supplier for PROD001 | `<Notes>Main supplier for PROD001</Notes>` |

### SupplierAddresses
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
<Suppliers 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Supplier>
    <Reference>ZYNK001</Reference>
    <Name>Zynk Software Ltd.</Name>
    <FirstName>Andrew</FirstName>
    <LastName>Snape</LastName>
    <Phone>0191 303 7279</Phone>
    <Mobile>0191 303 7279</Mobile>
    <Email>support@zynk.com</Email>
    <CreditLimit>1000</CreditLimit>
    <Notes>Main supplier for PROD001</Notes>
    <SupplierAddresses>
      <SupplierAddress>
        <AddressLine1>i6</AddressLine1>
        <AddressLine2>6 - 8 Charlotte Square</AddressLine2>
        <AddressCity>Newcastle</AddressCity>
        <AddressRegion>Tyne and Wear</AddressRegion>
        <AddressPostcode>NE1 4XF</AddressPostcode>
        <AddressCountry>United Kingdom</AddressCountry>
        <AddressReference>WORK</AddressReference>
      </SupplierAddress>
    </SupplierAddresses>
  </Supplier>
</Suppliers>
```