---
slug: importing-stock-transactions-into-sage-50-uk
redirect_from: "/article/418-importing-stock-transactions-into-sage-50-uk"
title: Importing Stock Transactions into Sage 50 UK
---
This task will import stock transactions to Sage 50 that is supplied in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.  

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Stock Transaction XML](sage-50-uk-stock-transaction-xml):  

```xml
<?xml version="1.0"?>
<Company>
  <StockTransactions>
    <StockTransaction>
      <StockCode>PROD001</StockCode>
      <StockTransactionType>MovementIn</StockTransactionType>
      <StockTransactionDate>2014-01-01T00:00:00</StockTransactionDate>
      <Details>Test Product</Details>
      <Reference>Movement In</Reference>
      <Qty>20</Qty>
      <SalesPrice>15</SalesPrice>
      <CostPrice>10</CostPrice>
    </StockTransaction>
  </StockTransactions>
</Company>
```