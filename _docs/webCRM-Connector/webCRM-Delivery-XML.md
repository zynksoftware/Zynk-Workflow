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
| numeric | 1 | `<GmRevenue1>1</GmRevenue1>` |

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

### ExtraCustom1 - ExtraCustom8
_Optional_  
There are up to eight extra custom fields available per organisation in webCRM.  If enabled at the task level, exports will attempt to include the label of the field as setup in the webCRM admin in the Name attribute.

// TODO
| Type | Example | XML |
| --- | --- | --- |
| string | JOE001 | `<ExtraCustom2 Name="Accounting ID Number">JOE001</ExtraCustom2>` |