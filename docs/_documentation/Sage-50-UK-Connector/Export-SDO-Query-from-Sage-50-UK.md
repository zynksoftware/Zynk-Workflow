---
slug: export-sdo-query-from-sage-50-uk
redirect_from: "/article/862-export-sdo-query"
title: Export SDO Query from Sage 50 UK
---
This task will export data using the Sage 50 SDO based on the settings you provide. This is mainly used to retrieve fields that are not available via ODBC.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export Data Type
_Required_  
The type of data you wish to export

 * **Customer**
 * **Invoice**
 * **Product**
 * **SalesOrder**

### Export Settings
_Required_  

 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.

### Fields
_Required_  
The list of fields you wish to export.

### Where
_Required_  
The collection of where clauses you wish to append to your query.

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
  <Records>
    <Record>
      <UniqueId>88</UniqueId>
      <Fields>
        <Field>
          <Name>INVOICE_NUMBER</Name>
          <Value>88</Value>
        </Field>
        <Field>
          <Name>ACCOUNT_REF</Name>
          <Value>JOE001</Value>
        </Field>
        <Field>
          <Name>EMAILED</Name>
          <Value>0</Value>
        </Field>
      </Fields>
    </Record>
  </Records>
</Company>
```