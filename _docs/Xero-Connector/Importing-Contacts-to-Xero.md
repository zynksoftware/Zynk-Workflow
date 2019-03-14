---
slug: importing-contacts-to-xero
redirect_from: "/article/353-uploading-contacts-to-xero"
title: Importing Contacts to Xero
---

This task will insert or update contacts in Xero.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Fail File
_Required_  
The file to save failed record imports to.

### Input File
_Required_  
The file containing the bank transactions to upload to Xero.

### Success File
_Required_  
The file to save successful record imports to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once, based on the ExternalId provided in the input XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples

A sample input file containing a contact is shown below. More detailed information about each field can be found in our [API Documentation](xero-contact-xml).

```xml
<ArrayOfXeroContact>
  <XeroContact>
    <ExternalId>8520</ExternalId>
    <Name>Zynk Software</Name>
    <EmailAddress>support@zynk.com</EmailAddress>
    <ContactPersons>
      <ContactPerson>
        <FirstName>Joe</FirstName>
        <LastName>Bloggs</LastName>
        <EmailAddress>support@zynk.com</EmailAddress>
        <IncludeInEmails>true</IncludeInEmails>
      </ContactPerson>
    </ContactPersons>
    <Addresses>
      <Address>
        <AddressType>Street</AddressType>
        <AddressLine1>Flemming Business Centre</AddressLine1>
        <AddressLine2>Jesmond</AddressLine2>
        <City>Newcastle</City>
        <Region>Tyne &amp; Wear</Region>
        <PostalCode>NE2 3AE</PostalCode>
        <Country>GB</Country>
      </Address>
    </Addresses>
    <Phones>
      <Phone>
        <PhoneType>Default</PhoneType>
        <PhoneNumber>1232920</PhoneNumber>
        <PhoneAreaCode>0845</PhoneAreaCode>
        <PhoneCountryCode />
      </Phone>
    </Phones>
  </XeroContact>
</ArrayOfXeroContact>
```
