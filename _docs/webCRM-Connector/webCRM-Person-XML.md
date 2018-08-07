---
slug: webcrm-person-xml
title: webCRM Person XML
---
A Person belongs to an Organisation in webCRM. You can have as many Person records related to an Organisation as you need.

In the B2B version of webCRM you must have at least an Organisation record – Person records are optional. 

If your system is B2C then a Person is the main entity on your records and all other module data links to the Person records in your system.

## Tasks
- [Exporting Persons from webCRM](exporting-persons-from-webcrm)
- [Importing Persons into webCRM](importing-persons-into-webcrm)

## Identifiers
The logic surrounding inserting/updating persons works as follows:
1. If an `<Id>1</Id>` is provided for the person, the existing person with this id will be updated.
2. If an `<ExternalId>1</ExternalId>` is provided for the person, and a match is found in Zynk's truth table, the existing person will be updated.
3. If a `LookupField="MemberNumber"`is provided Zynk will search for a match based on the data in the XML, and if a match is found the existing person will be updated.
4. If none of the above conditions are fulfilled a new person will be created.

## Fields
### @LookupField
 _Dependant_  
The field to use when searching webCRM for an existing record.  Can optionally be prepended with the table name e.g. `PersonMemberNumber` or `MemberNumber`

| Type | Example | XML |
| --- | --- | --- |
| string | MemberNumber | `LookupField="MemberNumber"` |

### @ExactMatch
_Dependant_  
Used with `@LookupField`, if set to true and more than one result is found when searching for a match the record will be rejected. defaults to `true`.

| Type | Example | XML |
| --- | --- | --- |
| bool | true | `ExactMatch="true"` |

### Id
_Dependant_  
The webCRM internal database identifier of the record.  If specified the record will be updated, otherwise Zynk will attempt to lookup the record or create a new one.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<Id>1</Id>` |

### ExternalId
_Dependant_  
Allows you to specify an external identifier that is used for preventing duplicate records being created.  If provided Zynk will store both the Id and ExternalId in the Truth database for future lookups.

| Type | Example | XML |
| --- | --- | --- |
| string | AS001 | `<ExternalId>AS001</ExternalId>` |

### CreatedAt
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-02-27T14:16:54+00:00 | `<CreatedAt>2018-02-27T14:16:54+00:00</CreatedAt>` |

### UpdatedAt
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-02-27T14:20:25+00:00 | `<UpdatedAt>2018-02-27T14:20:25+00:00</UpdatedAt>` |

### BlockMassEmail
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| bool | false | `<BlockMassEmail>false</BlockMassEmail>` |

### CampaignWrongPasswordCount
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<CampaignWrongPasswordCount>0</CampaignWrongPasswordCount>` |

### CheckMark1 - CheckMark10
_Optional_  
There are up to 10 check mark fields available per person in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | true | `<CheckMark7 Name="Key Accounting System Contact">true</CheckMark7>` |

### Comment
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Technical contact | `<Comment>Technical contact</Comment>` |

### CreatedBy
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | James | `<CreatedBy>James</CreatedBy>` |

### DirectPhone
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | 0191 303 7279 | `<DirectPhone>0191 303 7279</DirectPhone>` |

### Email
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | support@zynk.com | `<Email>support@zynk.com</Email>` |

### EmailBounces
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| bool | false | `<EmailBounces>false</EmailBounces>` |

### FirstName
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Andrew | `<FirstName>Andrew</FirstName>` |

### ImageFileExtension
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<ImageFileExtension></ImageFileExtension>` |

### LastLoginDateTime
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-02-27T14:20:25+00:00 | `<LastLoginDateTime>2018-02-27T14:20:25+00:00</LastLoginDateTime>` |

### LastName
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Snape | `<LastName>Snape</LastName>` |

### LoginLog
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<LoginLog />` |

### MarketDateId
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<MarketDateId />` |

### MemberGroupId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<MemberGroupId>0</MemberGroupId>` |

### MemberLanguageId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<MemberLanguageId>0</MemberLanguageId>` |

### MemberNumber
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<MemberNumber />` |

### MemberStartDate
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-02-27T14:20:25+00:00 | `<MemberStartDate>2018-02-27T14:20:25+00:00</MemberStartDate>` |

### MemberStatusId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<MemberStatusId>0</MemberStatusId>` |

### MemberWrongPasswordCount
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<MemberWrongPasswordCount>0</MemberWrongPasswordCount>` |

### MiddleName
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<MiddleName />` |

### MobilePhone
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<MobilePhone />` |

### Name
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | Andrew Snape | `<Name>Andrew Snape</Name>` |

### History
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<History />` |

### OrganisationId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<OrganisationId>0</OrganisationId>` |

### Salutation
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | Mr | `<Salutation>Mr</Salutation>` |

#### Values
Available values depend on your webCRM setup.

### Skype
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | zynksoftware | `<Skype>zynksoftware</Skype>` |

### SortOrder
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<SortOrder>0</SortOrder>` |

### Status
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | Active | `<Status>Active</Status>` |

#### Values
Available values depend on your webCRM setup.

### SupportLanguageId
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<SupportLanguageId>0</SupportLanguageId>` |

### TelephoneSearch
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | -01913037279- | `<TelephoneSearch>-01913037279-</TelephoneSearch>` |

### Title
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Developer | `<Title>Developer</Title>` |

### UpdatedBy
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | James Shaw | `<UpdatedBy>James Shaw</UpdatedBy>` |

### Plus1 - Plus20
_Optional_  
There are up to 20 plus custom fields available per person in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | 20180130 | `<Plus1 Name="Start Date">20180130</Plus1>` |

### CheckMark1 - CheckMark10
_Optional_  
There are up to 15 custom fields available per person in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | 4 | `<Custom1 Name="Role">4</Custom1>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Persons xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Person ExactMatch="true">
    <Id>4</Id>
    <CreatedAt>2018-08-06T17:18:57+01:00</CreatedAt>
    <UpdatedAt>2018-08-07T09:33:39+01:00</UpdatedAt>
    <BlockMassEmail>true</BlockMassEmail>
    <CampaignWrongPasswordCount>0</CampaignWrongPasswordCount>
    <CheckMark1>False</CheckMark1>
    <CheckMark2>False</CheckMark2>
    <CheckMark3>False</CheckMark3>
    <CheckMark4>False</CheckMark4>
    <CheckMark5>False</CheckMark5>
    <CheckMark6>False</CheckMark6>
    <CheckMark7 Name="Key Accounting System Contact">True</CheckMark7>
    <CheckMark8>False</CheckMark8>
    <CheckMark9>False</CheckMark9>
    <CheckMark10>False</CheckMark10>
    <Comment />
    <CreatedBy>James Shaw</CreatedBy>
    <DirectPhone>0191 303 7279</DirectPhone>
    <Email>support@zynk.com</Email>
    <EmailBounces>false</EmailBounces>
    <FirstName>Andrew</FirstName>
    <ImageFileExtension />
    <LastLoginDateTime>0001-01-01T00:00:00+00:00</LastLoginDateTime>
    <LastName>Snape</LastName>
    <LoginLog />
    <MarketDateId />
    <MemberGroupId>0</MemberGroupId>
    <MemberLanguageId>0</MemberLanguageId>
    <MemberNumber />
    <MemberStartDate>0001-01-01T00:00:00+00:00</MemberStartDate>
    <MemberStatusId>0</MemberStatusId>
    <MemberWrongPasswordCount>0</MemberWrongPasswordCount>
    <MiddleName />
    <MobilePhone />
    <Name>Andrew Snape</Name>
    <History />
    <OrganisationId>3</OrganisationId>
    <Salutation>Mr</Salutation>
    <Skype />
    <SortOrder>0</SortOrder>
    <Status>Active</Status>
    <SupportLanguageId>0</SupportLanguageId>
    <TelephoneSearch>-01913037279-</TelephoneSearch>
    <Title>Developer</Title>
    <UpdatedBy>James Shaw</UpdatedBy>
    <Plus1 Name="Start Date"></Plus1>
    <Custom1 Name="Role">4</Custom1>
    <Custom2></Custom2>
    <Custom3></Custom3>
    <Custom4></Custom4>
    <Custom5></Custom5>
    <Custom6></Custom6>
    <Custom7></Custom7>
    <Custom8></Custom8>
    <Custom9></Custom9>
    <Custom10></Custom10>
    <Custom11></Custom11>
    <Custom12></Custom12>
    <Custom13></Custom13>
    <Custom14></Custom14>
    <Custom15></Custom15>
    <Memo />
  </Person>
</Persons>
```