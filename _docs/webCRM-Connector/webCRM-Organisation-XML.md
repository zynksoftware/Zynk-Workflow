---
slug: webcrm-organisation-xml
title: webCRM Organisation XML
---
The term Organisations refers to company records in your webCRM system. In most cases Organisations are Prospects and Customers, but this term can also be used to refer to Partners, Resellers or Suppliers. 

In the B2B version of webCRM you must have at least an Organisation record – Person records are optional. All other module data links to the Organisation records in your system. 

You can organise your Organisation records into many different categories, for example by type, status, industry sector, territory, relationship to you, source and more. This enables you to understand the nature of your Contacts, manage ownership of the Data, and communicate effectively. 

## Tasks
- [Exporting Organisations from webCRM](exporting-organisations-from-webcrm)
- [Importing Organisations into webCRM](importing-organisations-into-webcrm)

## Identifiers
The logic surrounding inserting/updating organisations works as follows:
1. If an `<Id>1</Id>` is provided for the organisation, the existing organisation with this id will be updated.
2. If an `<ExternalId>1</ExternalId>` is provided for the organisation, and a match is found in Zynk's truth table, the existing organisation will be updated.
3. If a `LookupField="ExtraCustom2"`is provided Zynk will search for a match based on the data in the XML, and if a match is found the existing organisation will be updated.
4. If none of the above conditions are fulfilled a new organisation will be created.

## Fields
### @LookupField
 _Dependant_  
The field to use when searching webCRM for an existing record.  Can optionally be prepended with the table name e.g. `OrganisationExtraCustom2` or `ExtraCustom2`

| Type | Example | XML |
| --- | --- | --- |
| string | ExtraCustom2 | `LookupField="ExtraCustom2"` |

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
| string | JOE001 | `<ExternalId>JOE001</ExternalId>` |

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

### Address
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | Nelson House
Fleming Business Centre | `<Address>Nelson House
Fleming Business Centre</Address>` |

### Alert
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Unverified account | `<Alert>Unverified account</Alert>` |

### ApprovalStatus
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<ApprovalStatus>0</ApprovalStatus>` |

### City
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Newcastle | `<City>Newcastle</City>` |

### Comment
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Originally called Internetware Ltd. | `<Comment>Originally called Internetware Ltd.</Comment>` |

### CompareName
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | ZYNKSOFTWARELIMITED | `<CompareName>ZYNKSOFTWARELIMITED</CompareName>` |

### Country
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | United Kingdom | `<Country>United Kingdom</Country>` |

### CreatedBy
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | api2 Zynk | `<CreatedBy>api2 Zynk</CreatedBy>` |

### DivisionName
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | North | `<DivisionName>North</DivisionName>` |

### Domain
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | zynk.com | `<Domain>zynk.com</Domain>` |

### ExtraCustom1 - ExtraCustom8
_Optional_  
There are up to eight extra custom fields available per organisation in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | JOE001 | `<ExtraCustom2 Name="Accounting ID Number">JOE001</ExtraCustom2>` |

### Fax
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | 0845 123 2920 | `<Fax>0845 123 2920</Fax>` |

### Gps
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | 54.9783, -1.6178 | `<Gps>54.9783, -1.6178</Gps>` |

### Industry
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | IT | `<Industry>IT</Industry>` |

#### Values
Available values depend on your webCRM setup.

### LastDisplayedAt
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-03-06T16:39:46+00:00 | `<LastDisplayedAt>2018-03-06T16:39:46+00:00</LastDisplayedAt>` |

### LastItemType
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | SupportCase | `<LastItemType>SupportCase</LastItemType>` |

#### Available Values
 * Delivery
 * SupportCase

### LastItemUpdatedAt
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-01-26T11:43:37+00:00 | `LastItemUpdatedAt>2018-01-26T11:43:37+00:00</LastItemUpdatedAt>` |

### Name
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Zynk Software Limited | `<Name>Zynk Software Limited</Name>` |

### NoAds
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| bool | false | `<NoAds>false</NoAds>` |

#### Available Values
 * true
 * false

### History
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<History />` |

### PostCode
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | NE1 4XF | `<PostCode>NE1 4XF</PostCode>` |

### State
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Tyne and Wear | `<State>Tyne and Wear</State>` |

### Status
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | Prospect | `<Status>Prospect</Status>` |

#### Values
Available values depend on your webCRM setup.

### Telephone
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | 0191 303 7279 | `<Telephone>0191 303 7279</Telephone>` |

### TelephoneSearch
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | -01913037279- | `<TelephoneSearch>-01913037279-</TelephoneSearch>` |

### Type
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | Customer | `<Type>Customer</Type>` |

#### Values
Available values depend on your webCRM setup.

### UpdatedBy
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | api2 Zynk | `<UpdatedBy>api2 Zynk</UpdatedBy>` |

### Www
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | http://zynk.com | `<Www>http://zynk.com</Www>` |

### Plus1 - Plus20
_Optional_  
There are up to 20 plus custom fields available per organisation in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | 20180130 | `<Plus1 Name="Start Date">20180130</Plus1>` |

### Custom1 - Custom15
_Optional_  
There are up to 15 custom fields available per organisation in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | Advertising | `<Custom1 Name="Original Lead Source">Advertising</Custom1>` |

## Expandable Fields
Related information linked to organisations are also included in the downloaded XML.

### MainContact
_Read Only_
The primary contact associated with the organisation.  On an export this will be included if the settings have been enabled, and a match is found.  This field is not used on imports.

#### Example MainContact XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Organisations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Organisation ExactMatch="true">
    ...
    <MainPerson ExactMatch="true">
      ...
      <Id>3</Id>
      <FirstName>Andrew</FirstName>
      <LastName>Snape</LastName>
      ...
    </MainPerson>
    ...
  </Organisation>
</Organisations>
```

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Organisations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Organisation ExactMatch="true">
    <Id>2</Id>
    <CreatedAt>2016-12-08T14:20:58+00:00</CreatedAt>
    <UpdatedAt>2018-03-14T11:54:13+00:00</UpdatedAt>
    <Address>i6
6-8 Charlotte Square</Address>
    <Alert />
    <ApprovalStatus>0</ApprovalStatus>
    <City>Newcastle</City>
    <Comment />
    <CompareName>ZYNKSOFTWARELIMITEDNEWCASTLEUPONTYNE</CompareName>
    <Country>GB</Country>
    <CreatedBy>webCRM System</CreatedBy>
    <DivisionName>Newcastle upon Tyne</DivisionName>
    <Domain />
    <ExtraCustom1 Name="VAT no.">12345</ExtraCustom1>
    <ExtraCustom2 Name="Accounting ID Number">12345</ExtraCustom2>
    <ExtraCustom3></ExtraCustom3>
    <ExtraCustom4></ExtraCustom4>
    <ExtraCustom5></ExtraCustom5>
    <ExtraCustom6></ExtraCustom6>
    <ExtraCustom7></ExtraCustom7>
    <ExtraCustom8></ExtraCustom8>
    <Fax />
    <Gps />
    <ImageFileExtension />
    <Industry>IT</Industry>
    <LastDisplayedAt>2018-03-14T11:53:51+00:00</LastDisplayedAt>
    <LastItemType>SupportCase</LastItemType>
    <LastItemUpdatedAt>2018-01-26T11:43:37+00:00</LastItemUpdatedAt>
    <MarketDataId />
    <Name>Zynk Software Limited</Name>
    <NoAds>true</NoAds>
    <History />
    <OutlookSync>0</OutlookSync>
    <OverlayUrl />
    <Owner>3</Owner>
    <Owner2>0</Owner2>
    <PostCode>NE1 4XF</PostCode>
    <ReportTemp>0</ReportTemp>
    <Sla>0</Sla>
    <State>Tyne and Wear</State>
    <Status>Prospect</Status>
    <Telephone>0191 303 7279</Telephone>
    <TelephoneSearch>-01913037279-</TelephoneSearch>
    <TerritoryId>1</TerritoryId>
    <Type>Customer</Type>
    <UpdatedBy>api2 Zynk</UpdatedBy>
    <VatCountry>test</VatCountry>
    <VatGroup>test</VatGroup>
    <VatNumber />
    <VatStatus />
    <VatVerifiedAt>0001-01-01T00:00:00+00:00</VatVerifiedAt>
    <Www>http://zynk.com</Www>
    <XDate1>01/01/0001 00:00:00</XDate1>
    <XDate2>01/01/0001 00:00:00</XDate2>
    <XInt1>0</XInt1>
    <XInt2>0</XInt2>
    <XInt3>0</XInt3>
    <XInt4>0</XInt4>
    <XInt5>0</XInt5>
    <XInt6>0</XInt6>
    <XInt7>0</XInt7>
    <XInt8>0</XInt8>
    <XMemo1></XMemo1>
    <XMemo2></XMemo2>
    <XText1></XText1>
    <XText2></XText2>
    <XText3></XText3>
    <XText4></XText4>
    <XText5></XText5>
    <XText6></XText6>
    <XText7></XText7>
    <XText8></XText8>
    <Plus1 Name="Test Date">20180130</Plus1>
    <Custom1 Name="Original Lead Source">Advertising</Custom1>
    <Custom2 Name="No of Employess">51 to 100</Custom2>
    <Custom3 Name="Test">A1D001</Custom3>
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
    <Memo>test memo</Memo>
  </Organisation>
</Organisations>
```