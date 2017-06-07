---
slug: ms-sql-execute-scalar
redirect_from: "/article/320-ms-sql-execute-scalar"
title: MS SQL Execute Scalar
---
This task will execute a scalar query (a query which returns a single result) against SQL Server. This is useful for fetching data to be used in Dashboards

## Settings
### Operation Timeout
_Required_  
The maximum time to wait for the query to execute.

### Query
_Required_  
The SQL Query to be executed. See below for an example.

### Connection
_Required_  
The SQL Connection to use.  See the [[Connecting to SQL Server](connecting-to-sql-server) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [SQL Server Connector](using-sql-connector) tutorial.

Sample query, which will return the total balance across all accounts:

```sql
SELECT SUM(Balance) FROM Accounts
```