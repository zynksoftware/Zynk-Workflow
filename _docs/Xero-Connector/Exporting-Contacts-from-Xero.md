---
slug: exporting-contacts-from-xero
redirect_from: "/article/344-downloading-contacts-from-xero"
title: Exporting Contacts from Xero
---


This task will download contacts from Xero in XML format.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Export All
_Required_
Set to true to export all records, or false to only export records since the time shown in the Export From setting.

### Export From
_Required_
The rolling date to export modified records from. This will update automatically when the task runs. This setting only takes affect when Export All is set to false.

### Filter
_Optional_  
Specify criteria to filter the accounts on e.g. 	`Type == "BANK" AND Name.Contains("Business")`

### Zynk Settings
See [Common Task Settings](common-task-settings)



## Examples


Sample output file showing a contact:

```xml
<?xml version="1.0"?>
<ArrayOfXeroContact>
  <XeroContact>
    <UpdatedDateUtc>2014-09-08T20:24:38.037</UpdatedDateUtc>
    <Id>305ca5cf-497d-4fee-a161-cdb30e6be989</Id>
    <ContactStatus>Active</ContactStatus>
    <Name>Zynk Software</Name>
    <FirstName>Joe</FirstName>
    <LastName>Bloggs</LastName>
    <EmailAddress>support@zynk.com</EmailAddress>
    <BankAccountDetails />
    <IsSupplier>false</IsSupplier>
    <IsCustomer>true</IsCustomer>
    <Discount xsi:nil="true" />
    <HasAttachments>false</HasAttachments>
    <Balances>
      <AccountsReceivable>
        <Outstanding>914.55</Outstanding>
        <Overdue>0.00</Overdue>
      </AccountsReceivable>
      <AccountsPayable>
        <Outstanding>0.00</Outstanding>
        <Overdue>0.00</Overdue>
      </AccountsPayable>
    </Balances>
    <ContactPersons />
    <Addresses>
      <Address>
        <AddressType>Street</AddressType>
        <City />
        <Region />
        <PostalCode />
        <Country />
        <AttentionTo />
      </Address>
      <Address>
        <AddressType>PostOfficeBox</AddressType>
        <AddressLine1>Flemming Business Centre</AddressLine1>
        <AddressLine2>Jesmond</AddressLine2>
        <City>Newcastle</City>
        <Region />
        <PostalCode>NE2 3AE</PostalCode>
        <Country />
        <AttentionTo />
      </Address>
    </Addresses>
    <Phones>
      <Phone>
        <PhoneType>DirectDial</PhoneType>
        <PhoneNumber />
        <PhoneAreaCode />
        <PhoneCountryCode />
      </Phone>
      <Phone>
        <PhoneType>Default</PhoneType>
        <PhoneNumber>1232920</PhoneNumber>
        <PhoneAreaCode>0845</PhoneAreaCode>
        <PhoneCountryCode />
      </Phone>
      <Phone>
        <PhoneType>Fax</PhoneType>
        <PhoneNumber />
        <PhoneAreaCode />
        <PhoneCountryCode />
      </Phone>
      <Phone>
        <PhoneType>Mobile</PhoneType>
        <PhoneNumber>7777777</PhoneNumber>
        <PhoneAreaCode>07</PhoneAreaCode>
        <PhoneCountryCode />
      </Phone>
    </Phones>
    <ContactGroups>
      <ContactGroup>
        <Id>91dbdc3f-86c5-4bfe-b227-5d1735945cea</Id>
        <Name>Training</Name>
        <Status>ACTIVE</Status>
        <Contacts />
      </ContactGroup>
    </ContactGroups>
  </XeroContact>
</ArrayOfXeroContact>
```
