---
slug: connection-manager
redirect_from: "/article/49-connection-manager"
title: Connection Manager
---
Connections are used in Zynk to store the connection details for the systems you integrate with. Any task which requires a connection to an external system will have a setting which allows you to set the connection to use.

You can create a single connection to each system/data source and use this throughout Zynk in multiple workflows and tasks. Any changes you make to a connection will be picked up automatically by any task that uses them.

The first time a connection is required in a workflow Zynk will open a connection session which is reused across all related tasks, at the end of the workflow Zynk will close any connections that have been opened.

For information on creating and updating connections, see [Managing Connections](managing-connections).

## Properties
All connections have the following properties:

### Connection Type
This determines what system the connection is for. It controls which tasks can use the connection, for example a task from the Sage 50 connector will only accept connections of the Sage 50 type. When selecting the connection to use on a task, it will only show connections which can be used in conjunction with that task.

### Name
The name of the connection. Each connection must have a unique name.

### Default
Determines whether the connection will be selected automatically when adding new tasks to workflows. There can only be one default connection of each type.

## Selecting The Connection On A Task
Tasks which require a connection to an external system will have a setting which allows you to choose the connection to use. An example is shown below.

[![Select connection](http://www.zynk.com/images/v2/select_connection.png)](http://www.zynk.com/images/v2/select_connection.png)

1. Click on the connection setting, and open the drop-down. The names of connections which can be used will be displayed.
2. Double click on the connection you want the task use. If you want all tasks in the workflow to connect to the same data source, you can click the 'Set On All Tasks' button to apply the selected connection to all tasks.
3. If you haven't already created a connection to the external system you are integrating with, you can do this using the 'New' button.