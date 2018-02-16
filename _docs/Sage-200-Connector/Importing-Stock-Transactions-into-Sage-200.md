---
slug: importing-stock-transactions-into-sage-200
redirect_from: "/article/442-import-stock-transactions"
title: Importing Stock Transactions into Sage 200
---
This task will import new stock transaction records in Zynk XML format into Sage 200.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed stock transactions in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported stock transactions in Zynk XML format.

### Generate History Postings
_Required_  
Set to True if you want to create History Postings during the import.

### Generate Nominal Postings
_Required_  
Set to True if you want to create Nominal Postings during the import.

### Prevent Duplicates
_Required_  
Set to 'True' to check whether the stock transaction Id supplied in the  input XML file has already been imported, and if so skip the stock transaction.

### Warehouse Sort Type
_Required_  
Allows you to override which warehouse to use e.g. Default, Highest Quantity or Lowest Quantity.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a stock transaction is shown below. See our [Sage 200 Stock Transaction XML](sage-200-stock-transaction-xml) for more details on the Zynk XML Stock Transaction format for Sage 200.

```xml
<?xml version="1.0"?>
<Company>
  <StockTransactions>
    <StockTransaction>
      <Id>1</Id>
      <StockTransactionType>MovementIn</StockTransactionType>
      <StockCode>GREENFORK</StockCode>
      <Location>Warehouse</Location>
      <Bin>Unspecified</Bin>
      <Qty>20</Qty>
      <StockTransactionDate>2013-05-30T09:42:11</StockTransactionDate>
      <Reference>Movement In</Reference>
      <SecondReference>Adding Stock</SecondReference>
      <Details>+20 stock</Details>
      <AnalysisCode1>AC1</AnalysisCode1>
      <AnalysisCode2>AC2</AnalysisCode2>
      <AnalysisCode3>AC3</AnalysisCode3>
      <CostPrice>10</CostPrice>
    </StockTransaction>
  </StockTransactions>
</Company>
```