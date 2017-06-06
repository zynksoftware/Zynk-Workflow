---
slug: sage-50-uk-project-xml
title: Sage 50 UK Project XML
---
Import Projects allows you to create new and update existing Projects in Sage 50. 

Any Sage fields not documented below are not explicitly supported with our imports.

Sample file for importing/updating a Project:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Projects>
    <Project>
      <Id>1</Id>
      <Reference>ZYNK</Reference>
      <Name>ZYNK PROJECT</Name>
      <Description>ZYNK PROJECT - INTEGRATION</Description>
      <StartDate>2014-01-13T00:00:00</StartDate>
      <EndDate>2014-01-14T00:00:00</EndDate>
      <Status>ACTIVE</Status>
      <AccountReference>CUST0001</AccountReference>
      <SecondReference>SECONDREF</SecondReference>
      <ProjectAddress>
        <ContactName>Mr Chris Hotchkiss</ContactName>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE2 3AE</Postcode>
        <Telephone>0845 123 2920</Telephone>
        <Fax>0845 123 2921</Fax>
        <Email>support@zynk.com</Email>
        <Country>GB</Country>
      </ProjectAddress>
      <QuotedPrice>6778</QuotedPrice>
      <Analysis1>ANALYSIS1</Analysis1>
      <Analysis2>ANALYSIS2</Analysis2>
      <Analysis3>ANALYSIS3</Analysis3>
    </Project>
  </Projects>
</Company>
```

In each of the following sections, most of the XML has been omitted to make the samples easier to read. The whole structure of the Zynk XML Company schema is used below, as a reference of where fields should be in the object model.

## Project Details

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| N/A | Id | 1 | string | 255 | Optional | Id for the project from the third party system |
| Project Ref | Reference | ZYNK | string | 12 | Required | If a project with the specified reference exists, the project will be updated otherwise a new project is created.   Reference will always be upper case |
| Name | Name | ZYNK PROJECT | string | 255 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Description | Description | ZYNK PROJECT - INTEGRATION | string | 255 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Start Date | StartDate | 2014-01-13T00:00:00 | DateTime | 8 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to current date. Must be before or on the same date as the EndDate. |
| End Date | EndDate | 2014-01-14T00:00:00 | DateTime | 8 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to current date.  Must be after or on the same date as the StartDate. |
| Status | Status | ACTIVE | string | 12 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to the project status marked as default in Sage. Provided status must already be set up in Sage. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Projects>
    <Project>
      <Id>1</Id>
      <Reference>ZYNK</Reference>
      <Name>ZYNK PROJECT</Name>
      <Description>ZYNK PROJECT - INTEGRATION</Description>
      <StartDate>2014-01-13T00:00:00</StartDate>
      <EndDate>2014-01-14T00:00:00</EndDate>
      <Status>ACTIVE</Status>
    </Project>
  </Projects>
</Company>
```

## Customer Details  

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| A/C Ref | AccountReference | CUST0001 | string | 8 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. Provided account reference must be for a customer already set up in Sage |
| Order Number | SecondReference | SECONDREF | string | 30 | Required | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Projects>
    <Project>
      <AccountReference>CUST0001</AccountReference>
      <SecondReference>SECONDREF</SecondReference>
    </Project>
  </Projects>
</Company>
```

## Site Details  

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Contact name | ContactName | Mr Chris Hotchkiss | string | 30 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Street1 | Address1 | Nelson House, Fleming Business Centre | string | 60 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Street2 | Address2 | Jesmond | string | 60 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Town | Town | Newcastle upon Tyne | string | 60 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| County | County | Tyne & Wear | string | 60 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Post Code | Postcode | NE2 3AE | string | 60 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Telephone | Telephone | 0845 123 2920 | string | 30 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Fax | Fax | 0845 123 2921 | string | 30 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Email | Email | support@zynk.com | string | 255 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. Provided account reference must be for a customer already set up in                Sage |
| Country | Country | GB | string | 2 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to country code of country specified as the customer default in Sage. Provided country code must match a country code already set up in Sage |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Projects>
    <Project>
      <ProjectAddress>
        <ContactName>Mr Chris Hotchkiss</ContactName>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne & Wear</County>
        <Postcode>NE2 3AE</Postcode>        
        <Telephone>0845 123 2920</Telephone>
        <Fax>0845 123 2921</Fax>
        <Email>support@zynk.com</Email>
        <Country>GB</Country>
      </ProjectAddress>
    </Project>
  </Projects>
</Company>
```

## Revenue Totals 

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Price quoted | QuotedPrice | 6778 | double | 8 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to 0. Provided price must be greater than or equal to 0  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Projects>
    <Project>
      <QuotedPrice>6778</QuotedPrice>
    </Project>
  </Projects>
</Company>
```

## Analysis Types  

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Analysis 1 | Analysis1 | ANALYSIS1 | string | 30 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Analysis 2 | Analysis2 | ANALYSIS2 | string | 30 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |
| Analysis 3 | Analysis3 | ANALYSIS3 | string | 30 | Optional | If node not provided in XML and project exists, value stays the same. If node not provided in XML and project doesn't exist, default to empty. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Projects>
    <Project>
      <Analysis1>ANALYSIS1</Analysis1>
      <Analysis2>ANALYSIS2</Analysis2>
      <Analysis3>ANALYSIS3</Analysis3>
    </Project>
  </Projects>
</Company>
```