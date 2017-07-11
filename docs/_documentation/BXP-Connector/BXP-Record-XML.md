---
slug: bxp-record-xml
title: BXP Record XML
---
This task will update or insert records to a form in BXP, and update or insert related records from other forms. All the examples on this page use form ID 1, which represents orders, and form ID 2, which represents order item lines. A complete example is shown below which shows how to insert or update an order with OrderNumber 8290, and insert or update 2 item lines for the order. Subsequent examples demonstrate the separate parts of the XML in more detail.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Records FormId="1">
  <Record>
    <MatchField Name="OrderNumber" Value="8290" />
    <Field Name="CustomerId" Value="689" />
    <Field Name="Address1" Value="i6 Building" />
    <Field Name="Address2" Value="Charlotte Square" />
    <Field Name="City" Value="Newcastle-upon-Type" />
    <Field Name="State" Value="Tyne and Wear" />
    <Field Name="PostCode" Value="NE1 4XF" />
    <Field Name="CountryCode" Value="GB" />
    <Field Name="SubTotal" Value="150" />
    <Field Name="Shipping" Value="5" />
    <Field Name="ShippingVatRate" Value="20" />
    <Field Name="Total" Value="186" />
    <RelatedRecords FormId="2">
      <Record>
        <MatchField Name="OrderNumber" Value="8290" />
        <MatchField Name="SkuCode" Value="PROD001" />
        <Field Name="Quantity" Value="5" />
        <Field Name="UnitPrice" Value="10" />
        <Field Name="VatRate" Value="20" />
        <Field Name="SubTotal" Value="50" />
        <Field Name="Total" Value="60" />
      </Record>
      <Record>
        <MatchField Name="OrderNumber" Value="8290" />
        <MatchField Name="SkuCode" Value="PROD002" />
        <Field Name="Quantity" Value="2" />
        <Field Name="UnitPrice" Value="50" />
        <Field Name="VatRate" Value="20" />
        <Field Name="SubTotal" Value="100" />
        <Field Name="Total" Value="120" />
      </Record>
    </RelatedRecords>
  </Record>
</Records>
```

## Records
The Records element represents a collection of records to upload to BXP. This element is the root of the XML document. 

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| @FormId | 1 | integer | Required | The form ID to upload the of records contained within the collection. This should correspond with the ID of a form in BXP. |
| Record | See below | Record | Optional | Represents a record to upload to BXP. 0 or more Record elements can be included in the Records collection. See below for more information on the Record element. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Records FormId="1">
  <!-- Omitted -->
</Records>
```

## Record
The Record element represents an individual record to insert or update in BXP. 

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| ExternalId | 8290 | string | Optional | You can include the ID of the record from the source system here. This value will not be uploaded to BXP. Zynk will track it internally using the truth table, and will create a mapping between the ExternalId value and the ID assigned by BXP. If the a record with the same ExternalId is seen in future, it will be automatically matched to the existing record ID in BXP. Please note that if a matching ExternalId is found by Zynk, this will override any MatchField(s) provided. It will never override the BXP ID if this is explicitly provided as a Field. |
| MatchField | Name="OrderNumber" Value="8290" | string | Optional | Represents the name and value of a field that is used for matching to existing records in BXP. If more than one MatchField is specified, it will look for a matching record in BXP where all of the MatchFields match. The fields used should represent a unique value or a unique combination of values. If this is not the case, Zynk will return an error. |
| Field | Name="Address1" Value="i6 Building" | string | Optional | Represents the name and value of a field that should be updated in BXP. You can use the ID of the parent record as the value for a field by specifying `{ParentId}` as the value. |
| RelatedRecords | See below | RelatedRecords | Optional | Any related records to be uploaded to BXP can be included in the RelatedRecords collection. See below for more information. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Records FormId="1">
  <Record>
    <ExternalId>8290</ExternalId>
    <MatchField Name="OrderNumber" Value="8290" />
    <Field Name="CustomerId" Value="689" />
    <RelatedRecords FormId="2">
      <!-- Omitted -->
    </RelatedRecords>
  </Record>
</Records>
```

## RelatedRecords
The RelatedRecords element represents a collection of related records to upload to a different form in BXP. 

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| @FormId | 2 | integer | Required | The form ID to upload the of records contained within the collection. This should correspond with the ID of a form in BXP. |
| Record | See above | Record | Optional | Represents a related record to upload to BXP. 0 or more Record elements can be included in the Records collection. See above for more information on the Record element. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Records FormId="1">
  <Record>
    <RelatedRecords FormId="2">
      <!-- Omitted -->
    </RelatedRecords>
  </Record>
</Records>
```