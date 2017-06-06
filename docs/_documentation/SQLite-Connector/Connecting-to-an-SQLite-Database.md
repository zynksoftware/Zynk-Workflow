---
slug: connecting-to-an-sqlite-database
redirect_from: "/article/807-connecting-to-an-sqlite-database"
title: Connecting to an SQLite Database
---
All of the tasks in the SQLite connector require a connection to a SQLite database, so you will need to create a connection with the type 'SQLite Database'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your SQLite Database details:

![SQLite Connection](http://www.zynk.com/images/v2/sqlite_connection.png)

Enter your SQLite details as described below, then click 'Finish' to create the connection.

## Settings
### Fail If Missing
_Required_  
Set to true to raise an error if the database file does not already exist, or set to false to automatically creating a new database file.

### Pooling
_Required_  
Set to true to enable connection pooling.

### Source
_Required_  
Enter the path to the database file (e.g. `C:\Northwind.sl3`). 