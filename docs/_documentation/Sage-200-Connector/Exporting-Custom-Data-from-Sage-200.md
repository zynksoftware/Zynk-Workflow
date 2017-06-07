---
slug: exporting-custom-data-from-sage-200
redirect_from: "/article/429-exporting-custom-data-from-sage-200"
title: Exporting Custom Data from Sage 200
---
This task will export data from Sage 200 in XML format, as specified by an SQL Query. This is useful when there is no task which exports the data required.

The table and column names that can be used in the Query are determined by the Sage 200 database. They can be viewed using SQL Server Management Studio.

**Note** - The information below applies to version 1 of the task. Workflows created using Zynk 2.1.0 or above will contain version 2 of this task, please see 
[Exporting Custom Data from Sage 200 (V2)](exporting-custom-data-from-sage-200-v2) instead.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections.

### Export All
_Required_  
Set to true to export all records, or false to export records modified since the task last ran.

### Op Lock
_Optional_  
Used to export only modified records. Stores the highest OpLock value from the records exported, and will update automatically each time the task is ran.

### Op Lock Table
_Optional_  
The table to take the Op Lock value from. E.g. 	`[SLCustomerContact]`. Required when the Export All setting is set to false.

### Output File
_Required_  
The file to save the exported records to, in XML format.

### Export as Elements
_Required_  
Set to true to export the data as XML elements, or false to export data as XML attributes.

### Root
_Required_  
The name to give the root element in the output XML file. Defaults to 'Rows'.

### Row
_Required_  
The name to give the XML element for each row returned by the SQL query. Defaults to 'Row'.

### From
_Required_  
Enter the FROM clause of the SQL query, including any joins. The keyword FROM should not be included.	  
  
E.g. `[SLCustomerAccount] INNER JOIN [SLCustomerContact] ON [SLCustomerContact].[SLCustomerAccountID] = [SLCustomerAccount].[SLCustomerAccountID]`

### Group By
_Optional_  
Enter the GROUP BY clause of the SQL query. The keyword GROUP BY should not be included.

### Order By
_Optional_  
Enter the ORDER BY clause of the SQL query. The keyword ORDER BY should not be included.

### Select
_Required_  
Enter the SELECT clause of the SQL query. The keyword SELECT should not be included. Note that the query must always return an OpLock from the Sage database, even when exporting all records.	  
  
E.g. `[SLCustomerAccount].[CustomerAccountNumber], [SLCustomerContact].[ContactName], CONVERT(bigint, [SLCustomerContact].[OpLock]) AS [OpLock]`

### Where
_Optional_  
Enter the WHERE clause of the SQL query. The keyword WHERE should not be included.	  
E.g. `[CustomerAccountNumber] = 'ABC001'`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Example query, which selects the customer account reference and contact name(s), for the customer account ABC001:

```sql
SELECT [SLCustomerAccount].[CustomerAccountNumber], [SLCustomerContact].[ContactName], CONVERT(bigint, [SLCustomerContact].[OpLock]) AS [OpLock]
FROM [SLCustomerAccount] 
INNER JOIN [SLCustomerContact] ON [SLCustomerContact].[SLCustomerAccountID] = [SLCustomerAccount].[SLCustomerAccountID]
WHERE [CustomerAccountNumber] = 'ABC001'
```

Example output file when Export as Elements is set to false:

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row CustomerAccountNumber="ABC001" ContactName="John Smith" OpLock="186136"/>
  <Row CustomerAccountNumber="ABC001" ContactName="Joe Bloggs" OpLock="127188"/>
</Rows>
```

Example output file when Export as Elements is set to true:

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row> 
    <CustomerAccountNumber>ABC001</CustomerAccountNumber>
    <ContactName>John Smith</ContactName>
    <OpLock>186136</OpLock>
  </Row>
  <Row>
    <CustomerAccountNumber>ABC001</CustomerAccountNumber>
    <ContactName>Joe Bloggs</ContactName>
    <OpLock>127188</OpLock>
  </Row>
</Rows>
```