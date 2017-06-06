---
slug: odbc-execute
redirect_from: "/article/277-odbc-execute"
title: ODBC Execute
---
This task will execute a non-query against ODBC data source. It is typically used for stored procedures, insert, updates and delete commands.

## Settings
### Query
_Required_  
The SQL Query to be executed.

### Parameter Input File
_Required_  
Name of the file containing parameters if using parameterized queries.

### Connection
_Required_  
The ODBC Connection to use.  See the [Connecting to an ODBC Database](connecting-to-an-odbc-database) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample query, which will update the CreditLimit column in the Customers table where the Turnover is greater than 10000:

```sql
UPDATE Customers SET CreditLimit = 1000 WHERE Turnover > 10000
```