---
slug: exporting-currencies-from-sage-50-uk
redirect_from: "/article/394-exporting-currencies-from-sage-50-uk"
title: Exporting Currencies from Sage 50 UK
---
This task will export currencies from Sage 50 to Zynk XML format.

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
The name of the file to export to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <Currencies>
        <Currency>
            <UniqueId>GBP</UniqueId>
            <Number>1</Number>
            <Code>GBP</Code>
            <EmuMember>false</EmuMember>
            <ExchangeRate>1</ExchangeRate>
            <Locked xsi:nil="true" />
            <BaseCurrency>true</BaseCurrency>
            <MajorUnit>pounds</MajorUnit>
            <MinorUnit>pence</MinorUnit>
            <Name>Pound Sterling</Name>
            <Symbol>£</Symbol>
        </Currency>
        <Currency>
            <UniqueId>USD</UniqueId>
            <Number>2</Number>
            <Code>USD</Code>
            <EmuMember>false</EmuMember>
            <ExchangeRate>0</ExchangeRate>
            <Locked xsi:nil="true" />
            <BaseCurrency>false</BaseCurrency>
            <MajorUnit>dollars</MajorUnit>
            <MinorUnit>cents</MinorUnit>
            <Name>US Dollar</Name>
            <Symbol>buffer_0lt;/Symbol>
        </Currency>
        <Currency>
            <UniqueId>EUR</UniqueId>
            <Number>3</Number>
            <Code>EUR</Code>
            <EmuMember>true</EmuMember>
            <ExchangeRate>0</ExchangeRate>
            <Locked xsi:nil="true" />
            <BaseCurrency>false</BaseCurrency>
            <MajorUnit>euro</MajorUnit>
            <MinorUnit>cent</MinorUnit>
            <Name>Euro</Name>
            <Symbol>€</Symbol>
        </Currency>
    </Currencies>
</Company>
```