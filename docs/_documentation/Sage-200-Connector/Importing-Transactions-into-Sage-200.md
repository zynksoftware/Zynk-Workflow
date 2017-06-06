---
slug: importing-transactions-into-sage-200
redirect_from: "/article/444-import-transactions"
title: Importing Transactions into Sage 200
---
This task will import new transactions in Zynk XML format into Sage 200 as transactions.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed transactions in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported transactions in Zynk XML format.

### Allocate As Current User
_Required_  
Set to true to restrict the allocation routine to only allocate against transactions created by the current user.

### Allocate Transactions
_Required_  
Allows you to specify if transactions (payments or receipts) should be allocated to invoices.

### Auto Allocate
_Required_  
Allows you to use the Sage 200 automatic allocations function.

### Check References
_Required_  
Set to true to prevent transactions being imported where another transaction already exists in Sage with the same reference and type.

### Prevent Duplicates
_Required_  
Set to true to prevent transactions being imported where the Id is the same as another transaction previously imported by Zynk.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a transaction is shown below. See our [Sage 200 Transaction XML](sage-200-transaction-xml) for more details on the Zynk XML Transaction format for Sage 200.

```xml
<?xml version="1.0" encoding="utf-8"?> 
<Company>
  <Transactions>
    <Transaction>
      <Id>1</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>ANDREW</AccountReference>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate>
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>SI1</Reference>
      <SecondReference></SecondReference>
      <Details>Sales Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode>
      <TaxRate>20</TaxRate>
      <AnalysisCode>AC1</AnalysisCode>
    </Transaction>
  </Transactions>
</Company>
```