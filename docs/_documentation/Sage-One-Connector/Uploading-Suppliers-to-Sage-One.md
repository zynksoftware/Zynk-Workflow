---
slug: uploading-suppliers-to-sage-one
redirect_from: "/article/821-upload-suppliers"
title: Uploading Suppliers to Sage One
---
This task will upload suppliers that are supplied in the [Sage One Supplier XML](sage-one-supplier-xml) format.

## Fields
The below fields in bold are required when creating a suppliers, the other fields are optional when creating and updating. Please note, Zynk will always try and match your records based on the `Id` element in your XML. However, when using the Upload Suppliers task you can optionally select a field from the 'Match Contacts On' setting to match records.


* __Company__
* Email
* Mobile
* Name
* Notes
* TaxNumber
* Telephone
* __MainAddress__
* MainAddress/Address1
* MainAddress/Address2
* MainAddress/Town
* MainAddress/County
* MainAddress/Postcode
* MainAddress/Country/Id
* MainAddress/Country/Code
* MainAddress/Country/Name
* MainAddress/Email
* MainAddress/Telephone
* DeliveryAddress/Address1
* DeliveryAddress/Address2
* DeliveryAddress/Town
* DeliveryAddress/County
* DeliveryAddress/Postcode
* DeliveryAddress/Country/Id
* DeliveryAddress/Country/Code
* DeliveryAddress/Country/Name

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Match Contacts On
_Required_  
If no 'Id' node provided, match contacts based on this field. Either CompanyName, Telephone, Email or Postcode.

### Fail File
_Required_  
The name of a file for “failed” imports to be sent to.

### Input File
_Required_  
The source file that you want to import in Zynk XML format.

### Success File
_Required_  
The name of a file for “successful” imports to be sent to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage One Supplier XML](sage-one-supplier-xml) for full documentation of the XML format.
```xml
<?xml version="1.0"?>
<ArrayOfSupplier xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Supplier>
    <Id>SMITH01</Id>
    <Company>The Smiths</Company>
    <Name>Johnny Marr</Name>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <MainAddress>
      <Address1>Charming Man House</Address1>
      <Address2>123 Ask Road</Address2>
      <Town>Morrissey</Town>
      <County>Marrshire</County>
      <Postcode>NE29 2PQ</Postcode>
      <Country>
        <Name>United Kingdom</Name>
      </Country>
      <Email>johnny@thesmiths.co.uk</Email>
      <Telephone>0191 290 0618</Telephone>
    </MainAddress>
    <DeliveryAddress>
      <Address1>Asleep House</Address1>
      <Address2>123 Bigmouth Road</Address2>
      <Town>Morrissey</Town>
      <County>Marrshire</County>
      <Postcode>NE29 2RT</Postcode>
      <Country>
        <Name>United Kingdom</Name>
      </Country>
    </DeliveryAddress>
  </Supplier>
</ArrayOfSupplier>
```