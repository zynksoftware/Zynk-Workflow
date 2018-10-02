---
slug: salesforce-complex-object-xml
title: Salesforce Complex Object XML
---
This task will update or insert multiple records of different types in Salesforce, and create relationships between them. The example below shows how to upload opportunities and opportunity item lines, and link them to a particular account and pricebook.

```xml
<?xml version="1.0"?>
<SalesforceObjects xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Type="Opportunity" Key="Name">
    <SalesforceObject>
        <Fields>
            <Field Name="Name" Value="TEST Opp 12345" />
            <Field Name="CloseDate" Value="2016-08-10" />
            <Field Name="StageName" Value="Closed Won" />
            <LookupField Name="AccountId">
                <Criteria Type="Account">
                    <Fields>
                        <Field Name="Name" Value="Test 123" />
                    </Fields>
                </Criteria>
            </LookupField>
            <LookupField Name="Pricebook2Id">
                <Criteria Type="Pricebook2">
                    <Fields>
                        <Field Name="Name" Value="Standard Price Book" />
                    </Fields>
                </Criteria>
            </LookupField>
        </Fields>
        <Relationships>
            <Relationship Type="OpportunityLineItem">
                <SalesforceObject>
                    <Fields>
                        <LookupField Name="Id">
                            <Criteria Type="OpportunityLineItem">
                                <Fields>
                                    <Field Name="OpportunityId" Value="{ParentId}" />
                                    <LookupField Name="PricebookEntryId">
                                        <Criteria Type="PricebookEntry">
                                            <Fields>
                                                <Field Name="Pricebook2.Name" Value="Standard Price Book" />
                                                <Field Name="CurrencyIsoCode" Value="GBP" />
                                                <Field Name="Product2.ProductCode" Value="IPHONE4" />
                                            </Fields>
                                        </Criteria>
                                    </LookupField>
                                </Fields>
                            </Criteria>
                        </LookupField>
                        <Field Name="Description" Value="iPhone 4" />
                        <Field Name="OpportunityId" Value="{ParentId}" />
                        <Field Name="Quantity" Value="1" />
                        <Field Name="UnitPrice" Value="250" />
                        <LookupField Name="PricebookEntryId">
                            <Criteria Type="PricebookEntry">
                                <Fields>
                                    <Field Name="Pricebook2.Name" Value="Standard Price Book" />
                                    <Field Name="CurrencyIsoCode" Value="GBP" />
                                    <Field Name="Product2.ProductCode" Value="IPHONE4" />
                                </Fields>
                            </Criteria>
                        </LookupField>
                    </Fields>
                    <Relationships />
                </SalesforceObject>
            </Relationship>
        </Relationships>
    </SalesforceObject>
</SalesforceObjects>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the SalesforceObjects schema is used below as a reference of where fields should be in the object model.

## SalesforceObjects
The SalesforceObjects element represents a collection of objects to upload to Salesforce. This element is the root of the XML document.

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| @Type | Opportunity | string | Required | The type of objects contained within the collection. This should correspond with the API name of an object in Salesforce. |
| @Key | Name | string | Optional | Specify the Salesforce API field name of a field to use as the key. Defaults to Id if not specified. The key field will be used to match each SalesforceObject within the collection to existing records in Salesforce, so long as a value is specified for the key field in the Fields collection of the SalesforceObject. If a match is found, the existing record will be updated, otherwise a new record will be created. |
| SalesforceObject | N/A | SalesforceObject | Optional | A record to upload to Salesforce. 0 or more SalesforceObject elements can be included in the collection. See below for more information on the SalesforceObject element. |

```xml
<?xml version="1.0"?>
<SalesforceObjects xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Type="Opportunity" Key="Name">
    <SalesforceObject></SalesforceObject>
</SalesforceObjects>
```

## SalesforceObject
The SalesforceObject element represents an individual record to insert or update in Salesforce.

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| @OperationType | Insert | enum | Optional | The type of operation to perform against Salesforce. The available options are **Insert**, **Update** and **Upsert**. Will default to the option selected in the task settings if not specified. |
| Fields | N/A | Field or LookupField | Required | A collection of field values to set on the object in Salesforce. The collection can contain either Field or LookupField elements. |
| Relationships | N/A | Relationship | Optional | A collection of child records related to this record. The collection can contain 0 or more Relationship elements. See below for more information on the Relationship element. |

```xml
<?xml version="1.0"?>
<SalesforceObjects xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Type="Opportunity">
    <SalesforceObject OperationType="Insert">
        <Fields></Fields>
        <Relationships></Relationships>
    </SalesforceObject>
</SalesforceObjects>
```

## Field
The Field element represents the value of a field in Salesforce.

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| @Name | CloseDate | string | Required | The Salesforce API field name of the field in Salesforce. |
| @Value | 2016-08-10 | string | Optional | The value for the field. |
| @MatchCase | true | bool | Optional | When the Field appears within the Criteria collection of a LookupField, and the field type in Salesforce is a string or text area, this attribute is used to control whether the `@Value` provided is matched on a case sensitive basis. If not specified, the matching will not be case sensitive. |
| @PicklistMatchType | ApiName | enum | Optional | When the Field appears within the Criteria collection of a LookupField, and the field type in Salesforce is a picklist, this attribute is used to control how `@Value` is matched. **ApiName** will match the Value to the picklist's API names. **Value** will match the Value to the picklist's display values. **ApiNameThenValue** will firstly try to match based on API name, then fall back to the value if no match is found. **ValueThenApiName** will firstly try to match based on value, then fall back to the API name if no match is found. If not specified, the matching will default to 'ApiName'. |

```xml
<?xml version="1.0"?>
<SalesforceObjects xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Type="Opportunity">
    <SalesforceObject>
        <Fields>
            <Field Name="CloseDate" Value="2016-08-10" />
            <LookupField Name="AccountId">
                <Criteria Type="Account">
                    <Fields>
                        <Field Name="Name" Value="Test 123" MatchCase="true" />
                        <Field Name="Type" Value="Reseller" PicklistMatchType="ApiName" />
                    </Fields>
                </Criteria>
            </LookupField>
        </Fields>
    </SalesforceObject>
</SalesforceObjects>
```

## LookupField
The LookupField element represents a lookup for the value of a field from another object Salesforce. This is useful where you need to set a field to the same value as a field on another object in Salesforce. The example shown below will lookup the ID of the account with the name 'Test 123', and use this as the value for the AccountId field on an opportunity.

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| @Name | AccountId | string | Required | The Salesforce API field name of the field to update in Salesforce. |
| @Value | N/A | string | Optional | If a value is specified, this will be used instead of performing the lookup. |
| @LookupFieldType | Equals | enum | Optional | The type of comparison to perform when looking for a matching record in Salesforce. The available options are **Equals** and **Like**. Will default to 'Equals' if not specified. |
| Criteria/@Type | Account | string | Required | The type of object to perform the lookup on. This should correspond with the API name of an object in Salesforce. |
| Criteria/@Select | Id | string | Optional | The Salesforce API field name of the field containing the value to be returned by the lookup. If not specified, this will default to Id. |
| Criteria/@LookupType | Index | enum | Optional | The type of lookup to perform against Salesforce. **Exact** will return the first matching record, but will fail if more than one match is found. **First** will return the first matching record found. **Last** will return the last matching record found. **Index** will return the matching record from a specific index, as specified by the `@LookupIndex` attribute. Will default to 'Exact' if not specified. |
| Criteria/@LookupIndex | 1 | int | Optional | The index of the record the lookup should return. Use in conjunction with the **Index** LookupType. |
| Criteria/Fields | N/A | Field or LookupField | Required | The collection of field values to lookup records based on. At least one field must be specified, only records with field values matching all of those specified will be considered a match. Complex lookups across diferent types of object can be constructed by using further LookupField elements within the Fields collection. |

```xml
<?xml version="1.0"?>
<SalesforceObjects xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Type="Opportunity">
    <SalesforceObject>
        <Fields>
            <LookupField Name="AccountId" LookupFieldType="Index" LookupIndex="1">
                <Criteria Type="Account" Select="Id">
                    <Fields>
                        <Field Name="Name" Value="Test 123" MatchCase="true" />
                        <Field Name="Type" Value="Reseller" PicklistMatchType="ApiName" />
                    </Fields>
                </Criteria>
            </LookupField>
        </Fields>
    </SalesforceObject>
</SalesforceObjects>
```

## Relationship
The Relationship element represents an individual record that is a child of the SalesforceObject it is placed in. To create the relationship between the two records, you need make sure you set the value of the field that links the child to it's parent. You can access the Id of the parent record using the {ParentId} variable, as shown in the sample XML below.

| XML Field  | Example  | Field Type  | Input  | Description |
| --- | --- | --- | --- | --- |
| @Type | OpportunityLineItem | string | Required | The type of the child record. This should correspond with the API name of an object in Salesforce. |
| SalesforceObject | N/A | SalesforceObject | Required | The child record. See above for more information on the SalesforceObject element. |

```xml
<?xml version="1.0"?>
<SalesforceObjects xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Type="Opportunity">
    <SalesforceObject>
        <Relationships>
            <Relationship Type="OpportunityLineItem">
                <SalesforceObject>
                    <Fields>
                        <Field Name="OpportunityId" Value="{ParentId}" />
                    </Fields>
                </SalesforceObject>
            </Relationship>
        </Relationships>
    </SalesforceObject>
</SalesforceObjects>
```
