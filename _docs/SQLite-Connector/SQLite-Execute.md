---
slug: sqlite-execute
redirect_from: "/article/809-sqlite-execute"
title: SQLite Execute
---
This task will execute a non-result generating query against an SQLite database. It is typically used for stored procedures, insert, update and delete commands.

## Settings
### Query
_Required_  
The SQL query to be executed e.g. `UPDATE Customers SET CreditLimit = 1000 WHERE Turnover > 10000`

### Connection
_Required_  
The SQLite Connection to use. See the [Connecting to an SQLite Database](connecting-to-an-sqlite-database) article if you require more information on how to create/manage connections.

### Parameter Input File
_Required_  
Name of the file containing parameters if using parameterized queries.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample query is shown below, which will update the `Status` of an existing record in the `Orders` table of the database.
```sql
UPDATE Orders SET Status = 'Processed' WHERE OrderId = 1
```