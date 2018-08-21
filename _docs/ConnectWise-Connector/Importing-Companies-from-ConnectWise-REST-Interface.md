---
slug: importing-companies-via-connectwise-rest-interface
title: Importing Companies via ConnectWise REST Interface
---
This task will import companies into ConnectWise from an XML file. See below for a sample input file. 

Companies are created/updated based on the following rules:
* If an `<id>` is specified, the task will update the company with this ID.
* If an `<externalId>` is specified, and a corresponding entry is found in Zynk's truth table, the task will update the company with this ID.
* If one or more fields have been selected in the 'Match Companies On' setting, Zynk will search for a match based on the selected fields. If a matching company is found in ConnectWise, it will update the company.
* If none of the above conditions are met, the task will create a new company.

When updating existing companies, only writeable fields specified in the input file will be updated. Any other fields will keep their existing values.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the file to output any companies that failed to import. The error messages will be included in the file.

### Input File
_Required_  
The name of the file containing the companies to upload to ConnectWise. A sample file is provided below.

### Success File
_Required_  
The name of the file to output any successfully imported companies to.

### Match Companies On
_Optional_  
Use this setting to select the fields companies should be matched on. If more than one is specified, the task will search for companies where all of the fields match. The following fields are available:
* __identifier__ - This corresponds with the Company ID shown in ConnectWise Manage.
* __accountNumber__ - This corresponds with the Account ID shown in ConnectWise Manage.
* __vendorIdentifier__ - This corresponds with the Vendor ID shown in ConnectWise Manage.
* __name__ - This corresponds with the company name shown in ConnectWise Manage.
* __zip__ - This corresponds with the zip shown in the site in ConnectWise Manage.

### Prevent Reprocessing
_Required_  
Set this option to 'True' to prevent the same company being processed more than once by Zynk. An `<externalId>` must be provided in the input file for this to work.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Companies xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Company>
    <id>2</id>
    <externalId>MYCOM</externalId>
    <identifier>YourCompany</identifier>
    <name>Your Company</name>
    <status>
      <id>1</id>
      <name>Active</name>
    </status>
    <type>
      <id>5</id>
      <name>Partner</name>
    </type>
    <addressLine1>test</addressLine1>
    <addressLine2>test</addressLine2>
    <city>test</city>
    <state>MS</state>
    <zip>NE1 4XF</zip>
    <country>
      <id>1</id>
      <name>United States</name>
    </country>
    <phoneNumber>0191 303 7279</phoneNumber>
    <faxNumber />
    <website>http://www.example.com</website>
    <territoryId>38</territoryId>
    <marketId>23</marketId>
    <accountNumber>MYCOM</accountNumber>
    <defaultContact>
      <id>77</id>
      <name>Arnie Bellini</name>
    </defaultContact>
    <dateAcquired>2002-08-20T18:04:26Z</dateAcquired>
    <annualRevenue>0</annualRevenue>
    <numberOfEmployees xsi:nil="true" />
    <timeZone>
      <id>1</id>
      <name>US Eastern</name>
    </timeZone>
    <leadFlag>false</leadFlag>
    <unsubscribeFlag>false</unsubscribeFlag>
    <calendarId xsi:nil="true" />
    <vendorIdentifier />
    <taxIdentifier />
    <taxCode>
      <id>11</id>
      <name>Standard VAT</name>
    </taxCode>
    <billingTerms>
      <id>2</id>
      <name>Net 10</name>
    </billingTerms>
    <billToCompany>
      <id>2</id>
      <name>Your Company</name>
      <identifier>YourCompany</identifier>
    </billToCompany>
    <invoiceDeliveryMethod>
      <id>1</id>
      <name>Mail</name>
    </invoiceDeliveryMethod>
    <deletedFlag>false</deletedFlag>
    <dateDeleted xsi:nil="true" />
    <mobileGuid>f3bd951a-f535-446d-ba4e-fccb1f7ac954</mobileGuid>
    <customFields>
      <customField>
        <caption>Sage Ref</caption>
        <value>MYC001</value>
      </customField>
      <customField>
        <caption>CustomNumber</caption>
        <value>3.5</value>
      </customField>
    </customFields>
    <teams>
      <team>
        <teamRole>
          <name>Account Mgr</name>
        </teamRole>
        <member>
          <identifier>Admin1</identifier>
        </member>
        <locationId>0</locationId>
        <businessUnitId>0</businessUnitId>
      </team>
    </teams>
  </Company>
</Companies>
```
