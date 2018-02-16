---
slug: querying-records-in-salesforce
redirect_from: "/article/293-querying-records-in-salesforce"
title: Querying Records in Salesforce
---


This task will execute a Read query against the Salesforce system and return the data in XML format. The query must be written in Salesforce Object Query Language (SOQL). Documentation on the [Salesforce Object Query Language (SOQL)](https://developer.salesforce.com/docs/atlas.en-us.soql_sosl.meta/soql_sosl/) is provided by Salesforce.


## Settings

### Connection 
_Required_  
The Salesforce connection to use, see [Connecting to Salesforce](connecting-to-salesforce)

### Query
_Required_  
The Salesforce Object Query (SOQL) to be executed, supports nested queries and custom objects. e.g. 	`SELECT Id, Name FROM Account`

### Output File
_Required_  
The file name or variable to send the results of the query e.q Output.xml

### Zynk Settings 
See [Common Task Settings](common-task-settings)


## Examples
You can find an example of how to use this task in the [Salesforce to Sage 50 Integration](salesforce-to-sage-50-integration) article.

Sample SOQL query, to download closed won opportunities and their related account and item lines:

```sql
SELECT Account.Id, Account.AccountNumber, Account.Name,
  Account.Website, Account.Phone, Account.Fax,
  Account.BillingStreet, Account.BillingCity, Account.BillingState,
  Account.BillingCountry, Account.BillingPostalCode, 
  Opportunity.Id, Opportunity.Name, Opportunity.Owner.Name,
  Opportunity.CloseDate, Opportunity.HasOpportunityLineItem, Opportunity.Amount,
  (
    SELECT Quantity, ListPrice, UnitPrice,
    PriceBookEntry.Product2.Name, PriceBookEntry.Product2.ProductCode
    FROM OpportunityLineItems
  )
FROM Opportunity
WHERE StageName = 'Closed Won' AND Opportunity.Account.Id != null
```

Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<QueryResult>
  <done>true</done>
  <records type="Opportunity" url="/services/data/v20.0/sobjects/Opportunity/0068000000SvrwHAAR">
    <Id>0068000000SvrwHAAR</Id>
    <Account type="Account" rl="/services/data/v20.0/sobjects/Account/0018000000cGzpgAAC">
      <Id>0018000000cGzpgAAC</Id>
      <AccountNumber>000010</AccountNumber>
      <Name>Dura Limited</Name>
      <Website>http://www.duraltd.com</Website>
      <Phone>01112100100</Phone>
      <Fax>02222200200</Fax>
      <BillingStreet>123 Industrial Est.</BillingStreet>
      <BillingCity>Dura</BillingCity>
      <BillingState>County Dura</BillingState>
      <BillingCountry>England</BillingCountry>
      <BillingPostalCode>DU1 7TD</BillingPostalCode>
    </Account>
    <Name>Test Opp</Name>
    <Owner type="User" url="/services/data/v20.0/sobjects/User/00580000001nhfBAAQ">
      <Name>Andrew Snape</Name>
    </Owner>
    <CloseDate>2009-12-15</CloseDate>
    <HasOpportunityLineItem>true</HasOpportunityLineItem>
    <Amount>1860000.0</Amount>
    <OpportunityLineItems>
      <done>true</done>
      <records type="OpportunityLineItem" url="/services/data/v20.0/sobjects/OpportunityLineItem/00k8000000Dh12BAAR">
        <Quantity>12.0</Quantity>
        <ListPrice>150000.0</ListPrice>
        <UnitPrice>150000.0</UnitPrice>
        <PricebookEntry type="PricebookEntry" url="/services/data/v20.0/sobjects/PricebookEntry/01u80000002Nq17AAC">
          <Product2 type="Product2" url="/services/data/v20.0/sobjects/Product2/01t80000001LdRuAAK">
            <Name>GenWatt Gasoline 2000kW</Name>
            <ProductCode>GC5060</ProductCode>
          </Product2>
        </PricebookEntry>
      </records>
      <records type="OpportunityLineItem" url="/services/data/v20.0/sobjects/OpportunityLineItem/00k8000000Dh12AAAR">
        <Quantity>12.0</Quantity>
        <ListPrice>5000.0</ListPrice>
        <UnitPrice>5000.0</UnitPrice>
        <PricebookEntry type="PricebookEntry" url="/services/data/v20.0/sobjects/PricebookEntry/01u80000002Nq0tAAC">
          <Product2 type="Product2" url="/services/data/v20.0/sobjects/Product2/01t80000001LdRgAAK">
            <Name>GenWatt Diesel 10kW</Name>
            <ProductCode>GC1020</ProductCode>
          </Product2>
        </PricebookEntry>
      </records>
      <totalSize>2</totalSize>
    </OpportunityLineItems>
  </records>
  <totalSize>1</totalSize>
</QueryResult>
```