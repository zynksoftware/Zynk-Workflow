---
slug: using-sql-connector
redirect_from: "/article/643-using-sql-connector"
title: Using SQL Connector
---
The SQL Server connector in Zynk allows you to run queries against a Microsoft SQL Server database. This tutorial demonstrates how to use the tasks in this connector.

## MS SQL Select
The MS SQL Select task is used to run select queries against the database. In this example we select orders and their related items from the database. The results are saved to an XML file. The task settings are configured as follows:

 * **Output File** - This is the XML file to save the results of the query, and is set to `orders_query.xml`.
 * **Query** - This is the query to run on the database. It is set to   
`SELECT * FROM [Northwind].[dbo].[Orders] JOIN [Order Details] ON [Orders].[OrderID] = [Order Details].[OrderID]`
 * **Database** - This is the database to connect to, and is set to 'Northwind'.
 * **Instance** - Enter your SQL Server instance here. e.g. 127.0.0.1
 * **Password** - Enter your SQL Server password here. e.g. sa
 * **Username** - Enter your SQL Server username here. e.g. mysecret

## MS SQL Repeater
The MS SQL Repeater task is used to run a select query and loop through the results. In this example we loop through the suppliers and log a message stating how many products are supplied by them. The task settings are configured as follows:

 * **Query** - This is the query to run on the database. It is set to   
`SELECT [Suppliers].[SupplierID], [Suppliers].[CompanyName], Count([ProductID]) As [ProductCount] FROM [Suppliers] JOIN [Products] ON [Suppliers].[SupplierID] = [Products].[SupplierID] GROUP BY [Suppliers].[SupplierID], [Suppliers].[CompanyName]`
 * **Database** - This is the database to connect to, and is set to 'Northwind'.
 * **Instance** - Enter your SQL Server instance here.
 * **Password** - Enter your SQL Server password here.
 * **Username** - Enter your SQL Server username here.

The sub-task Log Info Message has the following setting:

 * **Input** - This is the message to log, and is set to `@(Context.Current["CompanyName"]) has @(Context.Current["ProductCount"]) products(s).`. The razor engine is used to get the value of the CompanyName and ProductCount context variables from the repeater task.

## MS SQL Execute Scalar
The MS SQL Execute Scalar task is used to get a single value from the database. In this example we use it to get a count of the number of customers. The output value is accessed using the 'Use output from previous task' option on the next task. The task settings are configured as follows:

 * **Query** - This is the query to run on the database. It is set to `SELECT Count(*) FROM [Customers]`.
 * **Database** - This is the database to connect to, and is set to 'Northwind'.
 * **Instance** - Enter your SQL Server instance here.
 * **Password** - Enter your SQL Server password here.
 * **Username** - Enter your SQL Server username here.