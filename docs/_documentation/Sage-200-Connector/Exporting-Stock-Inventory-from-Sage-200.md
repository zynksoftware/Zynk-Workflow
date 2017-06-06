---
slug: exporting-stock-inventory-from-sage-200
redirect_from: "/article/432-exporting-stock-inventory-from-sage-200"
title: Exporting Stock Inventory from Sage 200
---
This task will export new, modified or all stock inventory data in [Sage 200 XML](sage-200-xml) format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Characters To Cleanse
_Optional_  
A list of characters to remove from the output file. Use this if your Sage data contains characters that are not valid for XML documents (e.g. 	`&#x0;`).

### Export All Traceable
_Required_  
Set to true to export all traceable items, or false to only export modified records. Only takes effect when Export Traceable is set to true.

### Export Traceable
_Required_  
Set to true to include details of traceable items in the export.

### Export Settings
_Optional_  

 * **Date Created** - Used when exporting new records. Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.
 * **Op Lock** - Used when exporting modified records. Only records where the Op Lock is greater than this value will be exported. The value will update automatically each time the task runs.
 
### Query Settings
_Optional_  

 * **Columns** - Used to enter the column names to export from the Sage database. Be sure to include the table name eg. `[SLCustomerAccount].[CustomerAccountNumber]`
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported. 
  
### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Use Sales Trading Warehouse
_Required_  
Set to true to use warehouses marked for trading sales.

### Output File
_Required_  
The file to save the exported records to, in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Inventories>
    <Inventory>
      <UniqueId>6688</UniqueId>
      <Sku>PROD001</Sku>
      <Barcode />
      <Locations>
        <Location>
          <UniqueId>1006</UniqueId>
          <Name>WAREHOUS</Name>
          <QtyInStock>0</QtyInStock>
          <QtyOnOrder>36</QtyOnOrder>
          <QtyAllocated>0</QtyAllocated>
          <AllowSalesTrading>true</AllowSalesTrading>
          <Bins>
            <Bin>
              <UniqueId>6694</UniqueId>
              <Name>Unspecified</Name>
              <QtyInStock>0</QtyInStock>
              <QtyAllocated>0</QtyAllocated>
              <Batches />
            </Bin>
          </Bins>
        </Location>
      </Locations>
    </Inventory>
    <Inventory>
      <UniqueId>6429</UniqueId>
      <Sku>PROD0002</Sku>
      <Barcode />
      <Locations>
        <Location>
          <UniqueId>1006</UniqueId>
          <Name>WAREHOUS</Name>
          <QtyInStock>9</QtyInStock>
          <QtyOnOrder>10</QtyOnOrder>
          <QtyAllocated>0</QtyAllocated>
          <AllowSalesTrading>true</AllowSalesTrading>
          <Bins>
            <Bin>
              <UniqueId>6435</UniqueId>
              <Name>Unspecified</Name>
              <QtyInStock>9</QtyInStock>
              <QtyAllocated>0</QtyAllocated>
              <Batches />
            </Bin>
          </Bins>
        </Location>
      </Locations>
    </Inventory>
  </Inventories>
</Company>
```