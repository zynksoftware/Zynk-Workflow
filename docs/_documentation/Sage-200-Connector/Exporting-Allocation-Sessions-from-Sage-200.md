---
slug: exporting-allocation-sessions-from-sage-200
redirect_from: "/article/422-exporting-allocation-sessions-from-sage-200"
title: Exporting Allocation Sessions from Sage 200
---
This task will export the allocation session data when payments are allocated to invoices.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections.

### Characters To Cleanse
_Optional_  
A list of characters to remove from the output file. Use this if your Sage data contains characters that are not valid for XML documents (e.g. 	`&#x0;`).

### Export Settings
_Required_  

 * **Date Created** - Used when exporting new records. Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.
 * **Op Lock** - Used when exporting modified records. Only records where the Op Lock is greater than this value will be exported. The value will update automatically each time the task runs

### Query Settings
_Optional_  

 * **Columns** - Used to enter the column names to export from the Sage database. Be sure to include the table name (eg. [SLCustomerAccount].[CustomerAccountNumber])
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
<Company>
  <AllocationSessions>
    <AllocationSession>
      <UniqueId>5006</UniqueId>
      <AllocationDate>2013-11-07T00:00:00</AllocationDate>
      <AccountReference>WEBSALES</AccountReference>
      <AllocationType>ManualPayment</AllocationType>
      <AllocationTransactions>
        <AllocationTransaction>
          <UniqueId>4987</UniqueId>
          <TransactionNumber>4</TransactionNumber>
          <Reference>0000000003</Reference>
          <SecondReference>0000000009</SecondReference>
          <Value>12</Value>
          <AllocationValue>12</AllocationValue>
          <TransactionType>SalesInvoice</TransactionType>
        </AllocationTransaction>
        <AllocationTransaction>
          <UniqueId>4998</UniqueId>
          <TransactionNumber>5</TransactionNumber>
          <Reference>PAY</Reference>
          <SecondReference>0000000003</SecondReference>
          <Value>-12</Value>
          <AllocationValue>-12</AllocationValue>
          <TransactionType>SalesReceipt</TransactionType>
        </AllocationTransaction>
      </AllocationTransactions>
    </AllocationSession>
  </AllocationSessions>
</Company>
```