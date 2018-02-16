---
slug: ms-sql-repeater
redirect_from: "/article/321-ms-sql-repeater"
title: MS SQL Repeater
---
The SQL Server Repeater task will execute a Query against an SQL Server database and run series of sub-tasks for each row in the results. For example, you could use the query `SELECT Email FROM SALES_LEDGER` and the [Send Email](send-email) task as a sub-task to send an email to each customer in a database.

## Settings
### Operation Timeout
_Required_  
The maximum time to wait for the query to execute.

### Query
_Required_  
The SQL Query to be executed. See below for an example.  You can use the [Query Designer](using-the-query-designer) to build the query visually.

### Connection
_Required_  
The SQL Connection to use.  See the [[Connecting to SQL Server](connecting-to-sql-server) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
The task will convert each row to context variables, the name of the variables depend on the names of your columns in the query. To use these variables, reference them in templates as `@Context.Current["ColumnName"]` or within other task settings using the Razor option.

## Examples
You can find an example of how to use this task in the[SQL Server Connector](using-sql-connector) tutorial.

Sample query, which will select all data from the SLCustomerAccount table:

```sql
SELECT * FROM SLCustomerAccount
```