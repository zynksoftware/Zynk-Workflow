---
slug: uploading-customers-to-sage-one
redirect_from: "/article/820-upload-customers"
title: Uploading Customers to Sage One
---
This task will upload customers that are supplied in the [Sage One Customer XML](sage-one-customer-xml) format.

## Fields
* __Company__
* Name
* Notes
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
If no `Id` element is provided in the input file, contacts will be matched based on this field. Choose from either ContactName, Telephone, Email or Postcode.

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
A sample input file is shown below. See [Sage One Customer XML](sage-one-customer-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer>
    <Id>ZIGG01</Id>
    <Company>Ziggy Stardust and the Spiders from Mars</Company>
    <Name>Ziggy Stardust</Name>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <MainAddress>
      <Address1>Starman House</Address1>
      <Address2>123 Ziggy Street</Address2>
      <Town>Bowietown</Town>
      <County>Bowieshire</County>
      <Postcode>NE1 2DE</Postcode>
      <Country>
        <Code>GB</Code>
      </Country>
      <Email>z.stardust@thespidersfrommars.com</Email>
      <Telephone>0191 290 0614</Telephone>
    </MainAddress>
    <DeliveryAddress>
      <Address1>Spider House</Address1>
      <Address2>123 Mars Street</Address2>
      <Town>Bowietown</Town>
      <County>Bowieshire</County>
      <Postcode>NE5 6DE</Postcode>
      <Country>
        <Code>GB</Code>
      </Country>
    </DeliveryAddress>
  </Customer>
</ArrayOfCustomer>
```
 