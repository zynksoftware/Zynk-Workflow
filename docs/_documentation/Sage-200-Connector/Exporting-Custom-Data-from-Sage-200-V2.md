---
slug: exporting-custom-data-from-sage-200-v2
redirect_from: "/article/860-exporting-custom-data-from-sage-200-v2"
title: Exporting Custom Data from Sage 200 (V2)
---
This task will export data from Sage 200 in XML format, as specified by an SQL Query. This is useful when there is no task which exports the data required.

The table and column names that can be used in the Query are determined by the Sage 200 database. They can be viewed using SQL Server Management Studio.

**Note** - The information below applies to version 2 of the task. Workflows created using Zynk 2.0.3 or below will contain version 1 of this task, please see 
[Exporting Custom Data from Sage 200](exporting-custom-data-from-sage-200) instead.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections.

### Op Lock
_Required_  
This setting stores the highest OpLock value from the records the task has exported. It will update automatically each time the task is ran, provided your query returns the OpLock column from the database.

The OpLock value can be used to export modified records only. The task will pass this value to SQL Server as a query parameter called 'oplock'. You can use this in your query to only export records where the OpLock is greater than the value of this parameter. For example, the query below will only return customer accounts that have been modified since the task last ran.

`SELECT * FROM SLCustomerAccount WHERE SLCustomerAccount.OpLock > @oplock` 

### Op Lock Aliases
_Optional_  
If your query is joining to multiple tables, and you need to check for modified records across these tables, you can use this setting to specify the aliases used in the query for the OpLock columns from each table. These aliases will be taken into account when the Op Lock setting is automatically updated, and it will be set to the highest value across all the tables. For example when using the query below, you should add 	`ContactOpLock` to the list of aliases.  
  
```sql
SELECT [SLCustomerAccount].[SLCustomerAccountID], [SLCustomerAccount].[OpLock], [SLCustomerContact].[ContactName], [SLCustomerContact].[OpLock] AS [ContactOpLock]
FROM [SLCustomerAccount] 
INNER JOIN [SLCustomerContact] ON [SLCustomerContact].[SLCustomerAccountID] = [SLCustomerAccount].[SLCustomerAccountID]
WHERE [SLCustomerAccount].[OpLock] &gt; @oplock OR [SLCustomerContact].[OpLock] > @oplock
```
### Query
_Required_  
Enter the SQL query to run against the Sage 200 database.  E.g. `SELECT * FROM [SLCustomerAccount]`.  You can use the [Query Designer](using-the-query-designer).  

### Query Timeout
_Optional_  
Enter the length of time (in seconds) to allow the query to run for. If the query does not finish running before this time elapses, it will stop and an error will be reported back.

### Output File
_Required_  
The file to save the results of the query to. The data will be saved in XML format.

### Export as Elements
_Required_  
Set to true to export the data as XML elements, or false to export data as XML attributes.

### Root
_Required_  
The name to give the root element in the output XML file. Defaults to 'Rows'.

### Row
_Required_  
The name to give the XML element for each row returned by the SQL query. Defaults to 'Row'.

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