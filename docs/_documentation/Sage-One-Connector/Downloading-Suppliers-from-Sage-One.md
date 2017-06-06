---
slug: downloading-suppliers-from-sage-one
redirect_from: "/article/858-download-suppliers"
title: Downloading Suppliers from Sage One
---
This task will download Suppliers from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Download Detailed
_Required_  
Set to true to download detailed contact information. 

### Download Type
_Required_  
Select All, New or Modified.

### Record Id
_Optional_  
Optionally download a specific record by specifying the Sage One id.

### Output File
_Required_  
The file to save the downloaded records to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage One Supplier XML](sage-one-supplier-xml) for full documentaion of the XML format.
```xml
<?xml version="1.0"?>
<ArrayOfSupplier xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Supplier>
    <SageOneRecordId>9133252</SageOneRecordId>
    <Company>The Spiders From Mars</Company>
    <ContactType>Supplier</ContactType>
    <Name>Main Contact</Name>
    <Notes />
    <MainAddress>
      <Address1 />
      <Address2 />
      <Town />
      <County />
      <Postcode>NE4 5LD</Postcode>
      <Country />
      <Email>spiders@bowie.com</Email>
      <Telephone>0191 291 1758</Telephone>
      <Mobile />
    </MainAddress>
    <DeliveryAddress>
      <Address1 />
      <Address2 />
      <Town />
      <County />
      <Postcode />
      <Country />
    </DeliveryAddress>
  </Supplier>
  <Supplier>
    <SageOneRecordId>9148392</SageOneRecordId>
    <Company>The Smiths</Company>
    <ContactType>Supplier</ContactType>
    <Name>Johnny Marr</Name>
    <Notes />
    <MainAddress>
      <Address1>Charming Man House</Address1>
      <Address2>123 Ask Road</Address2>
      <Town>Morrissey</Town>
      <County>Marrshire</County>
      <Postcode>NE29 2PQ</Postcode>
      <Country />
      <Email>johnny@thesmiths.co.uk</Email>
      <Telephone>0191 290 0618</Telephone>
      <Mobile />
    </MainAddress>
    <DeliveryAddress>
      <Address1>Asleep House</Address1>
      <Address2>123 Bigmouth Road</Address2>
      <Town>Morrissey</Town>
      <County>Marrshire</County>
      <Postcode>NE29 2RT</Postcode>
      <Country />
    </DeliveryAddress>
  </Supplier>
</ArrayOfSupplier>
```