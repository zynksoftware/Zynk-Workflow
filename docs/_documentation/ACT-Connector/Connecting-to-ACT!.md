---
slug: connecting-to-act
redirect_from: "/article/448-connecting-to-act"
title: Connecting to ACT!
---
All of the tasks in the [ACT](act) connector require a Connection to ACT!. To find out more, see [Managing Connections](managing-connections).

You must specify the ACT! Connection you would like to use on each of the ACT! tasks. To specify the connection, select the appropriate entry from the dropdown as seen in the screenshot below. Alternatively, once you have set up the ACT! connection that you would like to use, you can make this the default for any tasks which require this connection type, which means that you don't need to select the connection for every new task that you add to the Workflow.

[![Select an ACT! connection for the task to use](http://www.zynk.com/images/v2/act/act-select-connection.png) ](http://www.zynk.com/images/v2/act/act-select-connection.png)

Alternatively, you can set up a new connection from here or edit the details of an existing connection.

When editing or setting up a new connection, you must specify a Name as seen in the screenshot below (**1.1**), this should be some identifying name for this particular connection. The check box seen in the screenshot below (**1.2**) is to mark the connection as the default for that connection type (ACT!).

[![Give the ACT! connection an identifying name](http://www.zynk.com/images/v2/act/act-name-connection.png) ](http://www.zynk.com/images/v2/act/act-name-connection.png)

You must then provide the Username (**2.1**) and Password (**2.2**) you would like to use to connect up to the ACT! data, the ACT! server hosting the data (**2.3**) and the name of the ACT! database (**2.4**) you would like to connect to.

[![Enter the ACT! credentials (username and password) you would like to use to connect to ACT! along with the ACT! server hosting the data and the name of the ACT! database you would like to connect to](http://www.zynk.com/images/v2/act/act-setup-connection.png)](http://www.zynk.com/images/v2/act/act-setup-connection.png)

## Connection Settings

### Username
_Required_  
The username to use when connecting up to ACT!. This must be an active user set up in ACT! with the relevant permissions needed for the tasks that will be performed by Zynk (**2.1**).  

### Password
_Required_  
The password for the provided ACT! user (**2.2**).  

### Host  
_Required_  
The name of the ACT! server where the ACT! data is hosted. If this is on the local computer where Zynk is running, leave as the default '.' (**2.3**).

### Name
_Required_  
The name of the ACT! database you are connecting to (**2.4**).

## Links
- [Introduction to the ACT! Connector](act)
- [Connecting to ACT!](connecting-to-act)
- [Importing Companies into ACT!](importing-companies-into-act)
- [Exporting Companies from ACT!](exporting-companies-from-act)
- [Importing Contacts into ACT!](importing-contacts-into-act)
- [Exporting Contacts from ACT!](exporting-contacts-from-act)
- [Importing Opportunities into ACT!](importing-opportunities-into-act)
- [Exporting Opportunities from ACT!](exporting-opportunities-from-act)
- [Importing Products into ACT!](importing-products-into-act)
- [Exporting Products from ACT!](exporting-products-from-act)