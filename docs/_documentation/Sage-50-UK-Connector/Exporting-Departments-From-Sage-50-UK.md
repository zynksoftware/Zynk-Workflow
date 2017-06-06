---
slug: exporting-departments-from-sage-50-uk
redirect_from: "/article/957-exporting-departments-from-sage-50-uk"
title: Exporting Departments From Sage 50 UK
---
This task will export departments from Sage 50 to Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new record

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
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Departments>
    <Department>
      <UniqueId>0</UniqueId>
      <Reference>0</Reference>
      <Name>Default</Name>
      <Number>0</Number>
      <Customers>
        <AccountReference>SCAPERSO</AccountReference>
        <AccountReference>TEST005</AccountReference>
      </Customers>
      <Suppliers>
        <AccountReference>TEST0001</AccountReference>
        <AccountReference>TEST0002</AccountReference>
        <AccountReference>TEST0003</AccountReference>
      </Suppliers>
    </Department>
  </Departments>
</Company>
```