---
slug: ms-sql-execute
redirect_from: "/article/319-ms-sql-execute"
title: MS SQL Execute
---
This task will execute a non-result generating query against SQL Server. It is typically used for stored procedures, insert, update and delete commands.

## Settings
### Operation Timeout
_Required_  
The maximum time to wait for the query to execute.

### Query
_Required_  
The SQL Query to be executed e.g. 	`UPDATE Customers SET CreditLimit = 1000 WHERE Turnover > 10000`

### Connection
_Required_  
The SQL Connection to use.  See the [[Connecting to SQL Server](connecting-to-sql-server) article if you require more information on how to create/manage connections.

### Parameter Input File
_Required_  
Name of the file containing parameters if using parameterized queries.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [SQL Server Connector](using-sql-connector) tutorial.

Sample query, which will update an existing record in the database:

```sql
UPDATE Orders SET Status = 'Processed' WHERE OrderId = 1
```