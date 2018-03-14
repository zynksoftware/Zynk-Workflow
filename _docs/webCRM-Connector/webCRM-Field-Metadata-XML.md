---
slug: webcrm-field-metadata-xml
title: webCRM Field Metadata XML
---
Field metadata is used to describe the fields that have been configured in webCRM, including any values provided for picklists etc.  You can use this task to help with identifying the names of custom fields, and the values that can be provided for fields.

## Tasks
- [Exporting Field Metadata from webCRM](exporting-field-metadata-from-webcrm)

## Fields
### DbFieldName
 _Read Only_  
The internal database name of the field.

| Type | Example | XML |
| --- | --- | --- |
| string | o_type | `<DbFieldName>o_type</DbFieldName` |

### FriendlyFieldName
 _Read Only_  
The friendly name for the field to use in queries.

| Type | Example | XML |
| --- | --- | --- |
| string | OrganisationType | `<FriendlyFieldName>OrganisationType</FriendlyFieldName>` |

### Id
 _Read Only_  
The internal id for the field.

| Type | Example | XML |
| --- | --- | --- |
| int | 12 | `<Id>12</Id>` |

### Label
 _Read Only_  
The label of the field used in webCRM UI.

| Type | Example | XML |
| --- | --- | --- |
| string | Org_Type | `<Label>Org_Type</Label>` |

### SortOrder
 _Read Only_  
The sort order of the field used in webCRM UI.

| Type | Example | XML |
| --- | --- | --- |
| int | 11090 | `<SortOrder>11090</SortOrder>` |

### DisplayType
 _Read Only_  
The display type of the field used in webCRM UI.

| Type | Example | XML |
| --- | --- | --- |
| string | D | `<DisplayType>D</DisplayType>` |

### TextFieldMaxLength
 _Read Only_  
The maximum length of text allowed for the field.

| Type | Example | XML |
| --- | --- | --- |
| int | 50 | `<TextFieldMaxLength>50</TextFieldMaxLength>` |

### DropdownListData
_Read Only_  
For certain field types values can be specified within webCRM, e.g. to build up drop down lists. 

#### Text
 _Read Only_  
The display text for the option.

| Type | Example | XML |
| --- | --- | --- |
| string | Customer | `<Text>Customer</Text>` |

#### Value
 _Read Only_  
The internal value for the option.

| Type | Example | XML |
| --- | --- | --- |
| string | Customer | `<Value>Customer</Value>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<FieldMetadata xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <FieldMetadata>
    <DbFieldName>o_type</DbFieldName>
    <FriendlyFieldName>OrganisationType</FriendlyFieldName>
    <Id>12</Id>
    <Label>Org_Type</Label>
    <SortOrder>11090</SortOrder>
    <DisplayType>D</DisplayType>
    <TextFieldMaxLength>50</TextFieldMaxLength>
    <DropdownListData>
      <FieldMetadataDropdownList>
        <Text>Customer</Text>
        <Value>Customer</Value>
      </FieldMetadataDropdownList>
      <FieldMetadataDropdownList>
        <Text>Partner</Text>
        <Value>Partner</Value>
      </FieldMetadataDropdownList>
      <FieldMetadataDropdownList>
        <Text>Supplier</Text>
        <Value>Supplier</Value>
      </FieldMetadataDropdownList>
      <FieldMetadataDropdownList>
        <Text>Agent</Text>
        <Value>Agent</Value>
      </FieldMetadataDropdownList>
      <FieldMetadataDropdownList>
        <Text>General</Text>
        <Value>General</Value>
      </FieldMetadataDropdownList>
    </DropdownListData>
  </FieldMetadata>
</FieldMetadata>
```