---
slug: exporting-customers-from-ekm
title: Exporting Customers from EKM
---
This task will export details of your customers to an XML file.

## Settings
### Connection
_Required_  
The EKM connection to use. See the [Connecting to EKM](connecting-to-ekm) article if you require more information on how to create/manage connections.

### Export Settings > Date Created
_Required_  
When the task is set to export new records, this is the date new records will be exported from. The value for this setting will update automatically when the task is ran.

### Export Settings > Date Modified
_Required_  
When the task is set to export modified records, this is the date modified records will be exported from. The value for this setting will update automatically when the task is ran.

### Export Settings > Export New, Modified or All Records
_Required_  
Select which records should be included in the export. The following options are available:
- **New** - Only records created since the date shown in the Date Created setting will be exported.
- **Modified** - Only records created or updated since the date shown in the Date Modified setting will be exported.
- **All** - All records will be exported.

### Page Size
_Required_  
The number of records to export on each page of data requested from EKM. The maximum value is 20.

### Query 
_Optional_  
Specify a custom filter to apply to the export. Only records meeting the criteria specified will be exported. The query must be specified using [OData](https://www.odata.org/getting-started/basic-tutorial/#filter) filter syntax. Please note that EKM only supports a subset of the OData filter syntax.

For example, you can use `first_name eq 'John'` to only export customers called 'John'. 

### Record IDs
_Optional_  
Specify a list of comma separated record IDs to export specific records from EKM. Using this setting will override the Query and Export Settings.

### Output File
_Required_  
The name of the file to output the exported data to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <Id>1</Id>
    <FirstName>Adam</FirstName>
    <LastName>Wardle</LastName>
    <EmailAddress>support@zynk.com</EmailAddress>
    <OrderCount>0</OrderCount>
    <LoyaltyPoints>0</LoyaltyPoints>
    <CreatedDate>2019-10-31T12:25:01Z</CreatedDate>
    <ModifiedDate>2019-10-31T12:25:01Z</ModifiedDate>
    <LastLoginDate>2019-10-31T12:25:01Z</LastLoginDate>
    <LastLoginAttemptDate>2019-10-31T12:25:01Z</LastLoginAttemptDate>
    <Locked>false</Locked>
    <LockedDate xsi:nil="true" />
    <LockedEndDate xsi:nil="true" />
    <IsSubscribedToNewsletter xsi:nil="true" />
    <Addresses>
      <Address>
        <Id>1</Id>
        <CustomerId>1</CustomerId>
        <FirstName>Adam</FirstName>
        <LastName>Wardle</LastName>
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
        <CreatedDate>2019-10-31T12:26:23Z</CreatedDate>
        <ModifiedDate>2019-10-31T12:26:23Z</ModifiedDate>
      </Address>
    </Addresses>
  </Customer>
</Customers>
```
