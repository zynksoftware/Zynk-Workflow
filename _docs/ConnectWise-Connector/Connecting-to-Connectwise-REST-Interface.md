---
slug: connecting-to-connectwise-rest-interface
title: Connecting to ConnectWise REST Interface
---

All of the REST tasks in the ConnectWise connector require a 'ConnectWise REST Interface' connection, so you will need to create a connection with this type when using those tasks. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below:

[![ConnectWise REST Interface Connection](http://www.zynk.com/images/v2/connectwise/rest-interface-connection.png)](http://www.zynk.com/images/v2/connectwise/rest-interface-connection.png)

Enter your ConnectWise details as described below, then click 'Finish' to create the connection.

## Settings

### Site
_Required_  
The ConnectWise Site URL that you will be connecting to, this will be the same as the Site you enter when logging into the ConnectWise Manage desktop application, or the same as the URL you enter in a browser to connect to the web portal.

### Company
_Required_  
The name of the ConnectWise Company you are connecting to, this will be the same as the Company you enter when logging into the ConnectWise Manage desktop application or web portal.

### Public Key
_Required_  
The public API key for the ConnectWise member Zynk should log in as. This can be generated under System > Members > [Member Name] > API Keys.

### Private Key
_Required_  
The private API key for the ConnectWise member Zynk should log in as. This can be generated under System > Members > [Member Name] > API Keys.