---
slug: exporting-purchase-return-notes-from-sage-200
redirect_from: "/article/674-exporting-purchase-return-notes-from-sage-200"
title: Exporting Purchase Return Notes from Sage 200
---
This task will export new, modified or all purchase return notes in [Sage 200 XML](sage-200-xml) format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Characters To Cleanse
_Optional_  
A list of characters to remove from the output file. Use this if your Sage data contains characters that are not valid for XML documents (e.g. 	`&#x0;`).

### Export Settings
_Optional_  

 * **Date Created** - Used when exporting new records. Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.
 * **Op Lock** - Used when exporting modified records. Only records where the Op Lock is greater than this value will be exported. The value will update automatically each time the task runs.
 
### Export Traceable Items  
_Required_  
Set to true to include the batch/serial numbers of traceable items in the exported data.

### Query Settings
_Optional_  

 * **Columns** - Used to enter the column names to export from the Sage database. Be sure to include the table name eg. `[SLCustomerAccount].[CustomerAccountNumber]`
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported. 
  
### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The file to save the exported records to, in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file, showing a return of product PROD001 for purchase return 0000000007:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <ReturnNotes>
    <ReturnNote>
      <UniqueId>1589484</UniqueId>
      <OrderNumber>0000000007</OrderNumber>
      <DocumentNumber>0000007852</DocumentNumber>
      <SupplierOrderNumber />
      <GoodsNotes>
        <GoodsNote>
          <UniqueId>1589485</UniqueId>
          <Type>GoodsReturnedNote</Type>
          <Date>2016-01-08T00:00:00</Date>
          <Sku>PROD001</Sku>
          <Quantity>9</Quantity>
        </GoodsNote>
      </GoodsNotes>
    </ReturnNote>
  </ReturnNotes>
</Company>
```