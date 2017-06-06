---
slug: sqlite-repeater
redirect_from: "/article/811-sqlite-repeater"
title: SQLite Repeater
---
The SQLite Repeater task will execute a query against an SQLite database and run series of sub-tasks for each row in the results. For example, you could use the query `SELECT Email FROM Customers` and the Send Email task as a sub-task to send an email to each customer in a database.

## Settings
### Query
_Required_  
The SQL query to be executed. See below for an example.

### Connection
_Required_  
The SQLite Connection to use. See the [Connecting to an SQLite Database](connecting-to-an-sqlite-database) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Context Variables
The task will convert each row returned by the query to a set of context variables, which allows the values returned to be used by the sub-tasks of the SQLite Repeater. The variable names will match the names of the columns returned by the query. 

The value of the context variables can be accessed using the following Razor code: `@Context.Current["ColumnName"]`. This can be used within Razor templates, or within task settings using the 'Use Razor Engine' option.

## Examples
A sample query is shown below, which will select the `Name` and `Email` data from the `CustomerAccount` table:
```sql
SELECT Name, Email FROM CustomerAccount
```