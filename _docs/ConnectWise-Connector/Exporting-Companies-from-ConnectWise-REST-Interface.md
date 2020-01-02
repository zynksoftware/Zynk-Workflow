---
slug: exporting-companies-from-connectwise-rest-interface
title: Exporting Companies from ConnectWise REST Interface
---
This task will export companies from ConnectWise in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Child Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding standard fields which are part of an array.

### Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding standard fields.

### Custom Field Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding custom fields.

#### Condition > Comparison
_Required_  
The following types of filter are available:

* __Contains__ - Returns records where the field contains the specified value.
* __Equal__ - Returns records where the field matches the specified value.
* __GreaterThan__ - Returns records where the field is greater than the specified value.
* __GreaterThanOrEqual__ - Returns records where the field is greater than or equal to the specified value.
* __In__ - Returns records where the field matches one of the specified values.
* __Like__ - Returns records where the field contains the specified value.
* __LessThan__ - Returns records where the field is less than the specified value.
* __LessThanOrEqual__ - Returns records where the field is less than or equal to the specified value.
* __NotContains__ - Returns records where the field does not contain the specified value.
* __NotEqual__ - Returns records where the field does not match the specified value.
* __NotIn__ - Returns records where the field does not match one of the specified values.
* __NotLike__ - Returns records where the field does not contain the specified value.

#### Condition > Field
_Required_  
The name of the field the condition is to be based upon. The name should match the API field name, as seen in the output file. If using a reference field, include the name of the reference field followed by a slash, then the field to filter on. e.g. `defaultContact/name`

#### Condition > Logic Operator
_Optional_  
The logic operator to use with the next condition when building the where clause. Choose from:

* __And__ - Will return records which meet all of the conditions specified.
* __Or__ - Will return records which meet at least one of the conditions specified.

#### Condition > Value
_Optional_  
The value the filter is to be based upon.

* String values should be surrounded by quotes. e.g. `"John"`
* Boolean values should be specified as either `True` or `False`, with no quotes.
* Datetime values should be specified in ISO8601 format, surrounded by square brackets. e.g. `[2000-01-31T14:51:00Z]`
* Null is specified as `null`.
* When using the In or NotIn comparison, specify a comma separated list of values surrounded by brackets. e.g. `("John", "Ben")`

### Export Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'New', only companies created after this date will be exported. This date will update automatically each time the task runs, to ensure only new companies are exported each time.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only companies updated after this date will be downloaded. This date will update automatically each time the task runs, to ensure only modified companies are exported each time.

### Export Settings > Export Modified, New or All Records
_Required_  
Choose which records should be downloaded. The available options are:

* __Modified__ - Only records updated after the date shown in the 'Date Modified' setting will be downloaded.
* __New__ - Only records created after the date shown in the 'Date Created' setting will be downloaded.
* __All__ - All records will be downloaded, regardless of when they were created or updated.

### Export Settings > Page Size
_Required_  
The number of records to include in each page of results. Defaults to 100. Increasing this value will reduce the number of requests made to the API. The maximum value is 1000.

### Output File
_Required_  
The name of the file to export the companies to.

### References To Fetch
_Optional_  
The exported data may include fields which reference other records in ConnectWise. If you specify the reference field names here, and the task will fetch the related records and include them in the exported data. The supported fields are listed below: 

* status
* type
* defaultContact
* parentCompany
* ownershipType
* timeZone
* taxCode
* billingTerms
* invoiceTemplate
* companyEntityType
* billToCompany
* billingSite
* billingContact
* invoiceDeliveryMethod
* currency
* territoryManager

### References To Fetch Page Size
_Required_  
The number of referenced records to fetch per page. Defaults to 100. Increasing this value will reduce the number of requests made to the API. The maximum value is 1000.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Companies xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Company>
    <id>2</id>
    <externalId>MYCOM</externalId>
    <_info>
      <dateEntered>2002-08-20T18:04:26Z</dateEntered>
      <enteredBy>CONVERSION</enteredBy>
      <lastUpdated>2018-05-01T14:33:38Z</lastUpdated>
      <updatedBy>Admin1</updatedBy>
    </_info>
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
    <zip />
    <country>
      <id>1</id>
      <name>United States</name>
    </country>
    <phoneNumber />
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
        <id>3</id>
        <caption>Sage Ref</caption>
        <type>Text</type>
        <entryMethod>EntryField</entryMethod>
        <numberOfDecimals>0</numberOfDecimals>
        <value>MYC001</value>
      </customField>
      <customField>
        <id>6</id>
        <caption>CustomNumber</caption>
        <type>Number</type>
        <entryMethod>EntryField</entryMethod>
        <numberOfDecimals>2</numberOfDecimals>
        <value>3.5</value>
      </customField>
    </customFields>
  </Company>
</Companies>
```
