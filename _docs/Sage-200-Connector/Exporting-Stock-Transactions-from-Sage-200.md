---
slug: exporting-stock-transactions-from-sage-200
redirect_from: "/article/434-exporting-stock-transactions-from-sage-200"
title: Exporting Stock Transactions from Sage 200
---
This task will export stock transactions in [Sage 200 XML](sage-200-xml) format.

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
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <StockTransactions>
    <StockTransaction>
      <UniqueId>1462</UniqueId>
      <StockTransactionType>GoodsIn</StockTransactionType>
      <StockCode>PROD001</StockCode>
      <StockTransactionDate>2013-10-10T00:00:00</StockTransactionDate>
      <Location>HOME</Location>
      <Bin>Unspecified</Bin>
      <Reference />
      <SecondReference />
      <Details />
      <AnalysisCode1 />
      <AnalysisCode2 />
      <AnalysisCode3 />
      <Qty>1000</Qty>
      <CostPrice>10</CostPrice>
      <SalesPrice xsi:nil="true" />
      <StockTransactionNumber xsi:nil="true" />
    </StockTransaction>
    <StockTransaction>
      <UniqueId>4638</UniqueId>
      <StockTransactionType>GoodsOut</StockTransactionType>
      <StockCode>PROD001</StockCode>
      <StockTransactionDate>2013-11-07T00:00:00</StockTransactionDate>
      <Location>HOME</Location>
      <Bin>Unspecified</Bin>
      <Reference>0000000008</Reference>
      <SecondReference>0000000001</SecondReference>
      <Details />
      <AnalysisCode1 />
      <AnalysisCode2 />
      <AnalysisCode3 />
      <Qty>5</Qty>
      <CostPrice>0</CostPrice>
      <SalesPrice xsi:nil="true" />
      <StockTransactionNumber xsi:nil="true" />
    </StockTransaction>
  </StockTransactions>
</Company>
```