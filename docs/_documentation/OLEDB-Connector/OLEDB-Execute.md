---
slug: oledb-execute
redirect_from: "/article/654-oledb-execute"
title: OLEDB Execute
---
This task will execute a non-query against OLEDB data source. It is typically used for stored procedures, insert, update and delete commands.

## Settings
### Query
_Required_  
The SQL query to be executed, see below for an example.

### Connection
_Required_  
The OLEDB Connection to use.  See the [Connecting to an OLEDB Database](connecting-to-an-oledb-database) article if you require more information on how to create/manage connections.

### Parameter Input File
_Optional_  
Name of the file containing parameters if using parameterized queries.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample query, which will set the CreditLimit in the Customers table to 1000 where the Turnover is greater than 10000:

```sql
UPDATE Customers SET CreditLimit = 1000 WHERE Turnover > 10000
```