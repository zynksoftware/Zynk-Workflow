---
slug: sqlite-execute-scalar
redirect_from: "/article/810-sqlite-execute-scalar"
title: SQLite Execute Scalar
---
This task will execute a scalar query (a query which returns a single result) against an SQLite database. This is useful for fetching data to be used in Dashboards.

## Settings
### Query
_Required_  
The SQL query to be executed. See below for an example.

### Connection
_Required_  
The SQLite Connection to use. See the [Connecting to an SQLite Database](connecting-to-an-sqlite-database) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample query is shown below, which will return the total `Balance` across all rows in the `Accounts` table.
```sql
SELECT SUM(Balance) FROM Accounts
```