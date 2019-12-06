---
slug: importing-customers-into-ekm
title: Importing Customers into EKM
---
This task will cerate or update customers in EKM.

## Settings
### Connection
_Required_  
The EKM connection to use. See the [Connecting to EKM](connecting-to-ekm) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any records which fail to import into EKM. Defaults to 'ekm_import_customers_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the records to import into EKM. Defaults to 'ekm_import_customers.xml'.

### Success File
_Required_  
The name of the XML file to save any records which successfully imported into EKM. Defaults to 'ekm_import_customers_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent the task from processing a record with the same `<ExternalId>` value as a previously imported record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <ExternalId>4362</ExternalId>
    <FirstName>John</FirstName>
    <LastName>Smith</LastName>
    <EmailAddress>john.smith@zynk.com</EmailAddress>
    <LoyaltyPoints>0</LoyaltyPoints>
    <Locked>false</Locked>
    <Addresses>
      <Address>
        <ExternalId>123</ExternalId>
        <FirstName>John</FirstName>
        <LastName>Smith</LastName>
        <Company>Zynk Software</Company>
        <Address>6-8 Charlotte Square</Address>
        <Address2 />
        <Town>Newcatle upon Tyne</Town>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <FriendlyCountry>United Kingdom</FriendlyCountry>
        <PostCode>NE1 4XF</PostCode>
        <Telephone>0191 303 7279</Telephone>
        <IsPreferredBillingAddress>true</IsPreferredBillingAddress>
        <IsPreferredShippingAddress>false</IsPreferredShippingAddress>
      </Address>
    </Addresses>
  </Customer>
</Customers>
```