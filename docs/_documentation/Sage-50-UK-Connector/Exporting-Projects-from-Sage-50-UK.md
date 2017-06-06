---
slug: exporting-projects-from-sage-50-uk
redirect_from: "/article/398-exporting-projects-from-sage-50-uk"
title: Exporting Projects from Sage 50 UK
---
This task will export project information from Sage 50 to Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.

### Query Settings
_Optional_  

 * **Columns** - Allows you to specify additional columns to include in the export.  Additional fields will be exported in the CustomFields section in the XML.  Be sure to include the table name for each of the additional columns provided eg. `[STOCK].[QTY_LAST_STOCK_TAKE]`.  If the table that the column you are trying to retrieve is not used by the standard export, you will need to add the table to Joins.
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported.

### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The name of the file to export to. Data is exported in Zynk XML format

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0"?>
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
      <AccountReference>CLIENT001</AccountReference>
      <SecondReference>SECONDREF</SecondReference>
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
      <QuotedPrice>6778</QuotedPrice>
      <Analysis1>ANALYSIS1</Analysis1>
      <Analysis2>ANALYSIS2</Analysis2>
      <Analysis3>ANALYSIS3</Analysis3>
    </Project>
  </Projects>
</Company>
```