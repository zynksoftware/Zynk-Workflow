---
slug: connecting-to-sql-server
redirect_from: "/article/658-connecting-to-sql-server"
title: Connecting to SQL Server
---
All of the tasks in the SQL Server connector require a connection to a SQL Server database, so you will need to create a connection with the type 'MS SQL Server'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your SQL Server details:

[![SQL Server Connection](http://www.zynk.com/images/v2/sql_server_connection.png)](http://www.zynk.com/images/v2/sql_server_connection.png)

Enter your SQL Server details as described below, then click 'Finish' to create the connection.

## Settings
### Additional Parameters
_Optional_  
Enter any additional parts of the connection string here. Alternatively, you can enter a full connection string here and leave the other fields blank (e.g. `server=CYAN\MSSQL2012;Database=TestCompany;User Id=sa;Password=p4ssw0rd`). See [connectionstrings.com](http://www.connectionstrings.com/) for more information about connection strings.

### Database
_Required_  
Enter the name of the database to connect to.

### Instance
_Required_  
Enter the name of the SQL server instance to connect to (e.g. PC-NAME\SQL-SERVER-INSTANCE). This is equivalent to the 'Server' parameter in the connection string.

### Password
_Required_  
Enter the password you use to connect to SQL Server.

### Username
_Required_  
Enter the username you use to connect to SQL Server.This is equivalent to the 'User Id' parameter in the connection string.