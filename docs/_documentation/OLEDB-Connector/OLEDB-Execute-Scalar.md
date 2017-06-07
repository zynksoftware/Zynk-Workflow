---
slug: oledb-execute-scalar
redirect_from: "/article/655-oledb-execute-scalar"
title: OLEDB Execute Scalar
---
This task will execute a scalar query (a query which returns a single result) on an OLEDB data source. The result can be accessed by the next task in the workflow using the 'Output from the previous task' option.

## Settings
### Query
_Required_  
The SQL query to be executed, see below for an example.

### Connection
_Required_  
The OLEDB Connection to use.  See the [Connecting to an OLEDB Database](connecting-to-an-oledb-database) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [OLEDB Connector](using-oledb-connector) tutorial.

Sample query, which will select the sum of the Balance column from the Accounts table:

```sql
SELECT SUM(Balance) FROM Accounts	
```