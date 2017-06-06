---
slug: downloading-customers-from-sage-one
redirect_from: "/article/851-download-customers"
title: Downloading Customers from Sage One
---
This task will download limited or detailed contact information from your instance of Sage One based on your settings. 

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
A sample output file is shown below. See [Sage One Customer XML](sage-one-customer-xml) for full documentaion of the XML format.
```xml
<?xml version="1.0"?>
<ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <SageOneRecordId>9147831</SageOneRecordId>
    <Company>Ziggy Stardust and the Spiders from Mars</Company>
    <ContactType>Customer</ContactType>
    <Name>Ziggy Stardust</Name>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <MainAddress>
      <Address1>Starman House</Address1>
      <Address2>123 Ziggy Street</Address2>
      <Town>Bowietown</Town>
      <County>Bowieshire</County>
      <Postcode>NE1 2DE</Postcode>
      <Country>
        <SageOneRecordId>218</SageOneRecordId>
        <Errors />
        <Code>GB</Code>
        <Name>United Kingdom</Name>
      </Country>
      <Email>z.stardust@thespidersfrommars.com</Email>
      <Telephone>0191 290 0614</Telephone>
      <Mobile />
    </MainAddress>
    <DeliveryAddress>
      <Address1>Spider House</Address1>
      <Address2>123 Mars Street</Address2>
      <Town>Bowietown</Town>
      <County>Bowieshire</County>
      <Postcode>NE5 6DE</Postcode>
      <Country>
        <SageOneRecordId>218</SageOneRecordId>
        <Errors />
        <Code>GB</Code>
        <Name>United Kingdom</Name>
      </Country>
    </DeliveryAddress>
  </Customer>
</ArrayOfCustomer>
```