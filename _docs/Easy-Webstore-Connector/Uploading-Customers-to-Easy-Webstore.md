---
slug: uploading-customers-to-easy-webstore
redirect_from: "/article/210-uploading-customers-to-easy-webstore"
title: Uploading Customers to Easy Webstore
---
This task will upload new customers to your store.

## Settings
### Connection
_Required_  
The Easy Webstore connection to use.  See the [Connecting to Easy Webstore](connecting-to-easy-webstore) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed customer uploads to.

### Input File
_Required_  
The XML file containing the new customers. The updates should be stored in the same format as customers downloaded using the 'Download Customers' task.

### Success File
_Required_  
The XML file to output successful customer uploads to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <ExtensionData />
    <BillingAddress1>Nelson House</BillingAddress1>
    <BillingAddress2>Fleming Business Centre</BillingAddress2>
    <BillingAddress3>Jesmond</BillingAddress3>
    <BillingCountry>United Kingdom</BillingCountry>
    <BillingCounty>Tyne & Wear</BillingCounty>
    <BillingPostcode>NE2 3AE</BillingPostcode>
    <BillingTown>Newcastle</BillingTown>
    <CompanyName>Zynk Software</CompanyName>
    <CustomData1 />
    <CustomData2 />
    <DeliveryAddress1>Nelson House</DeliveryAddress1>
    <DeliveryAddress2>Fleming Business Centre</DeliveryAddress2>
    <DeliveryAddress3>Jesmond</DeliveryAddress3>
    <DeliveryCountry>United Kingdom</DeliveryCountry>
    <DeliveryCounty>Tyne & Wear</DeliveryCounty>
    <DeliveryName>Joe Blogs</DeliveryName>
    <DeliveryPostcode>NE2 3AE</DeliveryPostcode>
    <DeliveryTown>Newcastle</DeliveryTown>
    <EmailAddress>joe.blogs@example.com</EmailAddress>
    <Fax>0123456789</Fax>
    <FirstName>Joe</FirstName>
    <LastName>Bloggs</LastName>
    <Message/ >
    <PromotionOptIn>false</PromotionOptIn>
    <Telephone>0123456789</Telephone>
    <Title>Mr</Title>
  </Customer>
</ArrayOfCustomer>
```