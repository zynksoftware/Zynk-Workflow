---
slug: webcrm-delivery-xml
title: webCRM Delivery XML
---
Deliveries are used to track post-sale activities and communications with your customers. It is important to focus not only on your marketing and sales processes, but also to ensure that your post-sale customer service is also well executed, managed and tracked.

webCRM can be configured to automatically create a delivery record whenever you update an opportunity pipeline level to won. 

## Tasks
- [Exporting Deliveries from webCRM](exporting-deliveries-from-webcrm)
- [Updating Deliveries in webCRM](updating-deliveries-in-webcrm)

## Identifiers
The logic surrounding updating deliveries works as follows:
1. If an `<Id>1</Id>` is provided for the delivery, the existing delivery with this id will be updated.
2. If a `LookupField="Number"`is provided Zynk will search for a match based on the data in the XML, and if a match is found the existing delivery will be updated.
3. If none of the above conditions are fulfilled the update will be discarded.

## Fields
### @LookupField
 _Dependant_  
The field to use when searching webCRM for an existing record.  Can optionally be prepended with the table name e.g. `DeliveryNumber` or `Number`

| Type | Example | XML |
| --- | --- | --- |
| string | Number | `LookupField="Number"` |

### @ExactMatch
_Dependant_  
Used with `@LookupField`, if set to true and more than one result is found when searching for a match the record will be rejected. defaults to `true`.

| Type | Example | XML |
| --- | --- | --- |
| bool | true | `ExactMatch="true"` |

### Id
_Dependant_  
The webCRM internal database identifier of the record.  If specified the record will be updated, otherwise Zynk will attempt to lookup the record.

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<Id>1</Id>` |

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

### AssignedTo
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 4 | `<AssignedTo>4</AssignedTo>` |

### AssignedTo2
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<AssignedTo2>0</AssignedTo2>` |

### Comment
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Comment></Comment>` |

### CreatedBy
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | Andrew Snape | `<CreatedBy>Andrew Snape</CreatedBy>` |

### CurrencyName
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 00 | `<CurrencyName>00</CurrencyName>` |

### Description
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Software sales | `<Description>Software sales</Description>` |

### Discount
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| decimal | 10 | `<Discount>10</Discount>` |

### ErpId
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | 000000001 | `<ErpId>000000001</ErpId>` |

### ErpReadOnly
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| bool | false | `<ErpReadOnly>false</ErpReadOnly>` |

### ErpStatus
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | NotReadyForSynchronization | `<ErpStatus>NotReadyForSynchronization</ErpStatus>` |

#### Values
Available values depend on your webCRM setup.

### ErpSyncDateTime
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-03-06T16:39:46+00:00 | `<ErpSyncDateTime>2018-03-06T16:39:46+00:00</ErpSyncDateTime>` |

### GmRevenue1 - GmRevenue12
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 100 | `<GmRevenue1>100</GmRevenue1>` |

### History
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| html | &lt;tr&gt;&lt;td&gt;08-12-2018&amp;nbsp;14:43&amp;nbsp;&lt;/td&gt;&lt;td&gt;SYS&amp;nbsp;&lt;/td&gt;&lt;td&gt;(JR)&amp;nbsp;9000&amp;nbsp;&lt;/td&gt;&lt;td colspan="2"&gt;New&amp;nbsp;&lt;/td&gt;&lt;td&gt;No risk&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;08-12-2016&amp;nbsp;14:42&amp;nbsp;&lt;/td&gt;&lt;td&gt;SYS&amp;nbsp;&lt;/td&gt;&lt;td&gt;(SYS)&amp;nbsp;9000&amp;nbsp;&lt;/td&gt;&lt;td colspan="2"&gt;New&amp;nbsp;&lt;/td&gt;&lt;td&gt;No risk&lt;/td&gt;&lt;/tr&gt; | `<History>&lt;tr&gt;&lt;td&gt;08-12-2018&amp;nbsp;14:43&amp;nbsp;&lt;/td&gt;&lt;td&gt;SYS&amp;nbsp;&lt;/td&gt;&lt;td&gt;(JR)&amp;nbsp;9000&amp;nbsp;&lt;/td&gt;&lt;td colspan="2"&gt;New&amp;nbsp;&lt;/td&gt;&lt;td&gt;No risk&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;08-12-2016&amp;nbsp;14:42&amp;nbsp;&lt;/td&gt;&lt;td&gt;SYS&amp;nbsp;&lt;/td&gt;&lt;td&gt;(SYS)&amp;nbsp;9000&amp;nbsp;&lt;/td&gt;&lt;td colspan="2"&gt;New&amp;nbsp;&lt;/td&gt;&lt;td&gt;No risk&lt;/td&gt;&lt;/tr&gt; </History>` |

### NextFollowUp
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-03-06T16:39:46+00:00 | `<NextFollowUp>2018-03-06T16:39:46+00:00</NextFollowUp>` |

### Note
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Partial delivery | `<Note>Partial delivery</Note>` |

### Number
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | 1001 | `<Number>1001</Number>` |

### OpportunityCustom1 - OpportunityCustom15
_Optional_  
There are up to 15 custom fields available per opportunity in webCRM which are available from deliveries.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | 12345 | `<OpportunityCustom1>12345</OpportunityCustom1>` |

### OpportunityMemo
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Partial delivery | `<OpportunityMemo>Partial delivery</OpportunityMemo>` |

### OrderDate
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-02-27T14:16:54+00:00 | `<OrderDate>2018-02-27T14:16:54+00:00</OrderDate>` |

### OrderGmValue
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 300 | `<OrderGmValue>300</OrderGmValue>` |

### OrderValue
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 600 | `<OrderValue>600</OrderValue>` |

### OrganisationId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<OrganisationId>1</OrganisationId>` |

### Percent
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 100 | `<Percent>100</Percent>` |

### PersonId
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 2 | `<PersonId>2</PersonId>` |

### Product
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Sample Product | `<Product>Sample Product</Product>` |

### ProductId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 2 | `<ProductId>2</ProductId>` |

### QuotationLanguageId
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<QuotationLanguageId>0</QuotationLanguageId>` |

### Responsible
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 2 | `<Responsible>2</Responsible>` |

### Revenue1
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 100 | `<Revenue1>100</Revenue1>` |

### Risk
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | NoRisk | `<Risk>NoRisk</Risk>` |

#### Values
Available values depend on your webCRM setup.

### Search1 & Search2
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | Sample Search | `<Search1>Sample Search</Search1>` |

### SpentTime
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| timespan | 01:30:00 | `<SpentTime>01:30:00</SpentTime>` |

### Status
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| picklist | New | `<Status>New</Status>` |

#### Values
Available values depend on your webCRM setup.

### Type
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<Type>0</Type>` |

### UpdatedBy
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | James | `<UpdatedBy>James</UpdatedBy>` |

### UserGroupId
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<UserGroupId>0</UserGroupId>` |

### WinPercent
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 100 | `<WinPercent>100</WinPercent>` |

### WinPercent2
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| int | 50 | `<WinPercent2>50</WinPercent2>` |

### WinYesNo
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| bool | true | `<WinYesNo>true</WinYesNo>` |

### WonDate
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-01-26T11:43:37+00:00 | `<WonDate>2018-01-26T11:43:37+00:00</WonDate>` |

### Custom1 - Custom15
_Optional_  
There are up to 15 custom fields available per delivery in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

| Type | Example | XML |
| --- | --- | --- |
| string | Project 2 | `<Custom1 Name="Project">Project 2</Custom1>` |

### Memo
_Optional_  

| Type | Example | XML |
| --- | --- | --- |
| string | First order | `<Memo>First order</Memo>` |

### Lines
_Optional_  
The lines associated with the order.  See [webCRM Quotation Line XML](webCRM-quotation-line-xml) for full details.

## Expandable Fields
Related information linked to deliveries are also included in the downloaded XML.

### Organisation
_Read Only_
The organisation associated with the delivery.  On an export will contain the information of the related organisation, his field is not used on updates.

#### Example Organisation XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Deliveries xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Delivery ExactMatch="true">
    ...
    <Organisation ExactMatch="true">
        ...
        <Id>1</Id>
        <Name>webCRM UK Limited</Name>
        ...
    </Organisation>
    ...
  </Delivery>
</Deliveries>
```

## Example XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Deliveries xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Delivery ExactMatch="true">
    <Id>2</Id>
    <CreatedAt>2016-12-08T14:42:14+00:00</CreatedAt>
    <UpdatedAt>2018-08-07T14:36:33+01:00</UpdatedAt>
    <AssignedTo>3</AssignedTo>
    <AssignedTo2>0</AssignedTo2>
    <Comment />
    <CreatedBy>webCRM System</CreatedBy>
    <CurrencyName>00</CurrencyName>
    <Description>Order</Description>
    <Discount>0</Discount>
    <ErpId>000000001</ErpId>
    <ErpReadOnly>false</ErpReadOnly>
    <ErpStatus>NotReadyForSynchronization</ErpStatus>
    <ErpSyncDateTime>2018-01-01T00:00:00+00:00</ErpSyncDateTime>
    <GmRevenue1>1</GmRevenue1>
    <GmRevenue2>2</GmRevenue2>
    <GmRevenue3>3</GmRevenue3>
    <GmRevenue4>4</GmRevenue4>
    <GmRevenue5>5</GmRevenue5>
    <GmRevenue6>6</GmRevenue6>
    <GmRevenue7>7</GmRevenue7>
    <GmRevenue8>8</GmRevenue8>
    <GmRevenue9>9</GmRevenue9>
    <GmRevenue10>10</GmRevenue10>
    <GmRevenue11>11</GmRevenue11>
    <GmRevenue12>12</GmRevenue12>
    <History>&lt;tr&gt;&lt;td&gt;07-08-2018&amp;nbsp;14:09&amp;nbsp;&lt;/td&gt;&lt;td&gt;JS&amp;nbsp;&lt;/td&gt;&lt;td&gt;(JS)&amp;nbsp;6000&amp;nbsp;&lt;/td&gt;&lt;td colspan="2"&gt;New / General&amp;nbsp;&lt;/td&gt;&lt;td&gt;No risk&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;08-12-2016&amp;nbsp;14:43&amp;nbsp;&lt;/td&gt;&lt;td&gt;SYS&amp;nbsp;&lt;/td&gt;&lt;td&gt;(JR)&amp;nbsp;9000&amp;nbsp;&lt;/td&gt;&lt;td colspan="2"&gt;New&amp;nbsp;&lt;/td&gt;&lt;td&gt;No risk&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;08-12-2016&amp;nbsp;14:42&amp;nbsp;&lt;/td&gt;&lt;td&gt;SYS&amp;nbsp;&lt;/td&gt;&lt;td&gt;(SYS)&amp;nbsp;9000&amp;nbsp;&lt;/td&gt;&lt;td colspan="2"&gt;New&amp;nbsp;&lt;/td&gt;&lt;td&gt;No risk&lt;/td&gt;&lt;/tr&gt; </History>
    <NextFollowUp>2018-01-01T00:00:00+00:00</NextFollowUp>
    <Note>Partial delivery</Note>
    <Number>1001</Number>
    <OpportunityCustom1>12345</OpportunityCustom1>
    <OpportunityCustom2>Quote</OpportunityCustom2>
    <OpportunityCustom3 />
    <OpportunityCustom4 />
    <OpportunityCustom5 />
    <OpportunityCustom6 />
    <OpportunityCustom7 />
    <OpportunityCustom8 />
    <OpportunityCustom9 />
    <OpportunityCustom10 />
    <OpportunityCustom11 />
    <OpportunityCustom12 />
    <OpportunityCustom13 />
    <OpportunityCustom14 />
    <OpportunityCustom15 />
    <OpportunityMemo>Partial delivery</OpportunityMemo>
    <OrderDate>2018-03-01T00:00:00+00:00</OrderDate>
    <OrderGmValue>300</OrderGmValue>
    <OrderValue>6000</OrderValue>
    <OrganisationId>1</OrganisationId>
    <Organisation ExactMatch="true">
      <Id>1</Id>
      <CreatedAt>2006-04-07T15:51:39+01:00</CreatedAt>
      <UpdatedAt>2016-12-08T14:37:56+00:00</UpdatedAt>
      <Address>Courtyard Business Centre</Address>
      <Alert />
      <ApprovalStatus>0</ApprovalStatus>
      <City>Nottingham</City>
      <Comment />
      <CompareName>WEBCRMUKLIMITEDMIDLANDS</CompareName>
      <Country>United Kingdom</Country>
      <CreatedBy>Jørgen Rode</CreatedBy>
      <DivisionName>Midlands</DivisionName>
      <Domain />
      <ExtraCustom1></ExtraCustom1>
      <ExtraCustom2></ExtraCustom2>
      <ExtraCustom3></ExtraCustom3>
      <ExtraCustom4></ExtraCustom4>
      <ExtraCustom5></ExtraCustom5>
      <ExtraCustom6></ExtraCustom6>
      <ExtraCustom7></ExtraCustom7>
      <ExtraCustom8></ExtraCustom8>
      <Fax />
      <Gps />
      <ImageFileExtension>No</ImageFileExtension>
      <Industry>IT</Industry>
      <LastDisplayedAt>2018-08-07T10:40:13+01:00</LastDisplayedAt>
      <LastItemType>Opportunity</LastItemType>
      <LastItemUpdatedAt>2018-08-06T15:22:58+01:00</LastItemUpdatedAt>
      <MarketDataId />
      <Name>webCRM UK Limited</Name>
      <NoAds>false</NoAds>
      <History />
      <OutlookSync>0</OutlookSync>
      <OverlayUrl />
      <Owner>3</Owner>
      <Owner2>0</Owner2>
      <PostCode>NG8 1PA</PostCode>
      <ReportTemp>0</ReportTemp>
      <Sla>0</Sla>
      <State>Nottinghamshire</State>
      <Status>Not relevant</Status>
      <Telephone>01158713702</Telephone>
      <TelephoneSearch>-01158713702-</TelephoneSearch>
      <TerritoryId>1</TerritoryId>
      <Type>Supplier</Type>
      <UpdatedBy>webCRM System</UpdatedBy>
      <VatCountry />
      <VatGroup />
      <VatNumber />
      <VatStatus />
      <VatVerifiedAt>0001-01-01T00:00:00+00:00</VatVerifiedAt>
      <Www>www.webcrm.com/uk</Www>
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
      <Custom1>Website</Custom1>
      <Custom2>51 to 100</Custom2>
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
    </Organisation>
    <Percent>55</Percent>
    <PersonId>1</PersonId>
    <Product>Your product 1</Product>
    <ProductId>0</ProductId>
    <QuotationLanguageId>2</QuotationLanguageId>
    <Responsible>3</Responsible>
    <Revenue1>1</Revenue1>
    <Revenue2>2</Revenue2>
    <Revenue3>3</Revenue3>
    <Revenue4>4</Revenue4>
    <Revenue5>5</Revenue5>
    <Revenue6>6</Revenue6>
    <Revenue7>7</Revenue7>
    <Revenue8>8</Revenue8>
    <Revenue9>9</Revenue9>
    <Revenue10>10</Revenue10>
    <Revenue11>11</Revenue11>
    <Revenue12>12</Revenue12>
    <Risk>NoRisk</Risk>
    <Search1>test</Search1>
    <Search2 />
    <SpentTime>01:30:00</SpentTime>
    <Status>New</Status>
    <Type>0</Type>
    <UpdatedBy>api2 Zynk</UpdatedBy>
    <UserGroupId>0</UserGroupId>
    <WinPercent>0</WinPercent>
    <WinPercent2>0</WinPercent2>
    <WinYesNo>false</WinYesNo>
    <WonDate>2018-01-01T00:00:00+00:00</WonDate>
    <Custom1 />
    <Custom2 />
    <Custom3 />
    <Custom4 />
    <Custom5 />
    <Custom6 />
    <Custom7 />
    <Custom8 />
    <Custom9 />
    <Custom10 />
    <Custom11 />
    <Custom12 />
    <Custom13 />
    <Custom14 />
    <Custom15 />
    <Memo>First order</Memo>
    <Lines>
      <QuotationLine ExactMatch="true">
        <Id>8</Id>
        <CreatedAt>2018-08-07T10:47:16+01:00</CreatedAt>
        <UpdatedAt>2018-08-07T10:47:16+01:00</UpdatedAt>
        <Comment />
        <CostPrice>50</CostPrice>
        <CreatedBy>James Shaw</CreatedBy>
        <Data1>End User</Data1>
        <Data2>Product 1</Data2>
        <Data3>12345</Data3>
        <Discount>0</Discount>
        <ListPrice>100</ListPrice>
        <Memo>Product 1 - Description Here</Memo>
        <OpportunityId>2</OpportunityId>
        <OrganisationId>1</OrganisationId>
        <PersonId>0</PersonId>
        <Price>100</Price>
        <Quantity>2</Quantity>
        <SortOrder>10</SortOrder>
        <StockStatus />
        <UpdatedBy>James Shaw</UpdatedBy>
        <VatPercentage>20</VatPercentage>
      </QuotationLine>
      <QuotationLine ExactMatch="true">
        <Id>9</Id>
        <CreatedAt>2018-08-07T10:47:16+01:00</CreatedAt>
        <UpdatedAt>2018-08-07T10:47:16+01:00</UpdatedAt>
        <Comment />
        <CostPrice>200</CostPrice>
        <CreatedBy>James Shaw</CreatedBy>
        <Data1>End User</Data1>
        <Data2>Service 1</Data2>
        <Data3>12353</Data3>
        <Discount>0</Discount>
        <ListPrice>400</ListPrice>
        <Memo>Product 9 - Description Here</Memo>
        <OpportunityId>2</OpportunityId>
        <OrganisationId>1</OrganisationId>
        <PersonId>0</PersonId>
        <Price>400</Price>
        <Quantity>1</Quantity>
        <SortOrder>20</SortOrder>
        <StockStatus />
        <UpdatedBy>James Shaw</UpdatedBy>
        <VatPercentage>20</VatPercentage>
      </QuotationLine>
    </Lines>
  </Delivery>
</Deliveries>
```