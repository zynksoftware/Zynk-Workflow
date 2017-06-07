---
slug: oledb-repeater
redirect_from: "/article/656-oledb-repeater"
title: OLEDB Repeater
---
The OLEDB Repeater task will execute a Query against an OLEDB database and run series of sub-tasks for each row in the results. For example, you could use the query `SELECT Email FROM SALES_LEDGER` and the Send Email task as a sub-task to send an email to each customer in a database.

## Settings
### Query
_Required_  
The SQL query to be executed, see below for an example.  You can use the [Query Designer](using-the-query-designer) to build the query visually.  

### Connection
_Required_  
The OLEDB Connection to use.  See the [Connecting to an OLEDB Database](connecting-to-an-oledb-database) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
The task will convert each row to context variables, the name of the variables depend on the names of your columns in the query. To use these variables, reference them in templates as `@Context.Current["ColumnName"]` or within other task settings using the Razor option.

## Examples
You can find an example of how to use this task in the [OLEDB Connector](using-oledb-connector) tutorial.

Sample query, which will select all records from the Customers table:

```sql    
SELECT * FROM Customers
```