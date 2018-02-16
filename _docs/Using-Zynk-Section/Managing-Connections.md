---
slug: managing-connections
redirect_from: "/article/56-managing-connections"
title: Managing Connections
---
Connections are used in Zynk to store the connection details for the systems you integrate with. You can view and edit your connections by clicking on the 'Connections' button on the main toolbar. You will see a window like the one below:

[![](http://www.zynk.com/images/v2/connection_manager.png)](http://www.zynk.com/images/v2/connection_manager.png)

## Creating A New Connection
To create a new connection, click the 'New' button on the toolbar. You will then see a window like the one below:

[![](http://www.zynk.com/images/v2/new_connection.png)](http://www.zynk.com/images/v2/new_connection.png)

1. Select the system you want to create a connection to from the 'Connection Type' drop down.
2. Enter a name for the connection. Note that each connection must have a unique name.
3. Choose whether this connection should be the default for new tasks which connect to the chosen system. Note that you can only have one default per connection type. If a default connection already exists for the chosen connection type, this new connection will become the new default.
4. Click the 'Next' button to proceed to the next page.
5. Enter the requested details in the boxes provided. This will depend on the system you are connecting to, refer to the documentation for the connector for more information.
6. Click the 'Finish' button to save the new connection.

## Editing An Existing Connection
To edit an existing connection, select a connection from the list, and click the 'Edit' button. The process for editing a connection is the same as when creating a new connection, so just follow the instructions above. Note that it is not possible to change the connection type.

## Deleting A Connection
To delete an existing connection, select one or more connections from the list, and click the 'Delete' button. You will see a message like the one below asking you to confirm the delete operation.

[![](http://www.zynk.com/images/v2/delete_connection.png)](http://www.zynk.com/images/v2/delete_connection.png)

Click 'Yes' to delete the connection.

## Importing/Exporting Connections
You can import and export connections to and from files, this allows you to copy connections from one PC to another. Please note that when importing connections, it will overwrite any connections which already exist. If you need to move an entire integration from one PC to another, it is simpler to use the import/export workflow functions which handle the transfer of connections automatically. See [Moving Workflows Between Computers](moving-workflows-between-computers) for details.

**Export Connections**
1. Select one or more connections from the list of connections.
2. Click the 'Export' button.
3. Choose a file to export the connections to, and click the 'Ok' button.

**Import Connections**
1. Click the 'Import' button.
2. Select the file containing the connections to import.
3. Click the 'Ok' button.