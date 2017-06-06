---
slug: exporting-stock-transactions-from-sage-50-uk
redirect_from: "/article/406-exporting-stock-transactions-from-sage-50-uk"
title: Exporting Stock Transactions from Sage 50 UK
---
This task will export stock transactions from Sage 50 in Zynk XML format.

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
    <StockTransactions>
        <StockTransaction>
            <UniqueId>1</UniqueId>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
            <StockCode>BOARD001</StockCode>
            <StockTransactionDate>2006-12-31T00:00:00</StockTransactionDate>
            <Reference>STK TAKE</Reference>
            <Details>Whiteboard - Drywipe (900 x 1200)</Details>
            <Qty>2</Qty>
            <CostPrice>15</CostPrice>
            <SalesPrice>0</SalesPrice>
            <StockTransactionNumber>1</StockTransactionNumber>
        </StockTransaction>
        <StockTransaction>
            <UniqueId>2</UniqueId>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
            <StockCode>BOARD002</StockCode>
            <StockTransactionDate>2006-12-31T00:00:00</StockTransactionDate>
            <Reference>STK TAKE</Reference>
            <Details>Whiteboard - Drywipe (1000 x 1500)</Details>
            <Qty>2</Qty>
            <CostPrice>17</CostPrice>
            <SalesPrice>0</SalesPrice>
            <StockTransactionNumber>2</StockTransactionNumber>
        </StockTransaction>
    </StockTransactions>
</Company>
```