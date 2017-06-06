---
slug: importing-complex-records-to-salesforce
redirect_from: "/article/899-uploading-complex-records-to-salesforce"
title: Importing Complex Records to Salesforce
---
This task will update or insert multiple records of different types in Salesforce, and create relationships between them. For example, you can use this task to upload opportunities and opportunity item lines, and link them to a particular account and pricebook.

Existing records are matched with those provided in the input file, based on the Salesforce field specified as the key field in the input file. If no key field is specified, the Id will be used for matching. If a match is found, the existing record will be updated, or if no match is found a new record will be inserted.

The task supports performing lookups for the Id of existing records in Salesforce, based on any fields of your choice. For example, if you know the account name when uploading an opportunity, you can use a lookup to set the value of the `AccountId` field based on the account name.

## Settings

### Connection 
_Required_  
The Salesforce connection to use, see [Connecting to Salesforce](connecting-to-salesforce)

### Fail File
_Required_  
The file to output any records to that fail to import to Salesforce.

### Input File
_Required_  
The file containing the record to import to Salesforce.

### Success File
_Required_  
The file to output successfully imported records to

### Zynk Settings 
See [Common Task Settings](common-task-settings)

## Examples
A sample input file containing opportunities and item lines is shown below. For detailed information on the XML schema, see [Salesforce Complex Object XML](salesforce-complex-object-xml).

```xml
<?xml version="1.0"?>
<SalesforceObjects xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Type="Opportunity" Key="Name">
  <SalesforceObject>
    <Fields>
      <Field Name="Name" Value="TEST Opp 12345" />
      <Field Name="CloseDate" Value="2016-08-10" />
      <Field Name="StageName" Value="Closed Won" />
      <LookupField Name="AccountId"> <!-- Lookup the account ID based on name -->
        <Criteria Type="Account">
          <Fields>
            <Field Name="Name" Value="Test 123" />
          </Fields>
        </Criteria>
      </LookupField>
      <LookupField Name="Pricebook2Id"> <!-- Lookup the pricebook ID based on name -->
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
            <LookupField Name="Id"> <!-- Lookup the Id of existing item lines based on the OpportunityId, and PricebookEntryId -->
              <Criteria Type="OpportunityLineItem">
                <Fields>
                  <Field Name="OpportunityId" Value="{ParentId}" /> <!-- The opportunity ID is the ID of the parent object -->
                  <LookupField Name="PricebookEntryId"> <!-- Lookup the PricebookEntryId based on the price book name, currency and product code -->
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
            <Field Name="OpportunityId" Value="{ParentId}" /> <!-- The opportunity ID is the ID of the parent object -->
            <Field Name="Quantity" Value="1" />
            <Field Name="UnitPrice" Value="250" />
            <LookupField Name="PricebookEntryId"> <!-- Lookup the PricebookEntryId based on the price book name, currency and product code -->
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