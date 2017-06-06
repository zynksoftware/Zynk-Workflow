---
slug: odbc-execute-scalar
redirect_from: "/article/278-odbc-execute-scalar"
title: ODBC Execute Scalar
---
This task will execute a scalar query (a query which returns a single result) on an ODBC data source. The result can be accessed by the next task in the workflow using the 'Output from the previous task' option.

To run a query which can return multiple rows and/or columns from the database, use the [ODBC Select](odbc-select) task instead.

## Settings
### Query
_Required_  
The SQL query to be executed. See below for an example.

### Connection
_Required_  
The ODBC Connection to use.  See the [Connecting to an ODBC Database](connecting-to-an-odbc-database) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [ODBC Connector](odbc-connector) tutorial.

Sample query, which will select the sum of the Balance column from the Accounts table:

```sql
SELECT SUM(Balance) FROM Accounts
```