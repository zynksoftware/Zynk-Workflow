---
slug: odbc-connector
redirect_from: "/article/644-odbc-connector"
title: ODBC Connector
---
The ODBC connector in Zynk allows you to connect to any ODBC data source. This tutorial demonstrates how to use the tasks in this connector to run queries against an ODBC databse. In each of the examples, we will use the Northwind database.

The sample workflow containing the tasks below can be downloaded from our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples).

## ODBC Select
The [ODBC Select](odbc-select) task is used to run select queries against the database. In this example we select orders and their related items from the database. The results are saved to an XML file. The task settings are configured as follows:

 * Output File - This is the XML file to save the results of the query, and is set to 'orders\_query.xml'.
 * Query - This is the query to run on the database. It is set to   
`SELECT * FROM Orders JOIN `Order Details` ON Orders.OrderID = `Order Details`.OrderID`
 * Connection String - Enter your ODBC connection string here.

## ODBC Repeater
The [ODBC Repeater](odbc-repeater) task is used to run a select query and loop through the results. In this example we loop through the suppliers and log a message stating how many products are supplied by them. The task settings are configured as follows:

 * Query - This is the query to run on the database. It is set to   
`SELECT Suppliers.SupplierID, Suppliers.CompanyName, Count(ProductID) As ProductCount FROM Suppliers JOIN Products ON Suppliers.SupplierID = Products.SupplierID GROUP BY Suppliers.SupplierID, Suppliers.CompanyName`
 * Connection String - Enter your ODBC connection string here.

The sub-task [Log Info Message](log-info-message) has the following setting:

 * Input - This is the message to log, and is set to `@(Context.Current["CompanyName"]) has @(Context.Current["ProductCount"]) products(s).`. The razor engine is used to get the value of the CompanyName and ProductCount context variables from the repeater task.

## ODBC Execute Scalar
The [ODBC Execute Scalar](odbc-execute-scalar) task is used to get a single value from the database. In this example we use it to get a count of the number of customers. The output value is accessed using the 'Use output from previous task' option on the next task. The task settings are configured as follows:

 * Query - This is the query to run on the database. It is set to `SELECT Count(*) FROM Customers`.
 * Connection String - Enter your ODBC connection string here.