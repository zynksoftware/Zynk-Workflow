---
slug: connecting-to-connectwise-accounting-interface
redirect_from: "/article/924-connecting-to-connectwise-accounting-interface"
title: Connecting to ConnectWise Accounting Interface
---


All of the tasks in the ConnectWise connector require a connection to ConnectWise. The type of connection required depends on the task being used. The ConnectWise Download GL Batch, ReCreate GL Batch, Update GL Batch and Update Invoice Payments Tasks use the 'ConnectWise Accounting Interface' connection type, so you will need to create a connection with this type when using those tasks. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below:



[![ConnectWise Accounting Interface Connection](http://www.zynk.com/images/v2/connectwise/accounting-interface-connection.png)](http://www.zynk.com/images/v2/connectwise/accounting-interface-connection.png)



Enter your ConnectWise details as described below, then click 'Finish' to create the connection.

## Settings

### Company
_Required_
The name of the ConnectWise Company you are connecting to, this will be the same as the Company you enter when logging into the desktop application or web portal.

### Username
_Required_
The name of the ConnectWise Member you will be logging in as. See the below section on ConnectWise Security Roles if you are unsure of how the access to the Accounting Interface API is determined.

### Password 
_Required_
The password of the ConnectWise Member you are logging in as.

### PSA Site
_Required_
The ConnectWise Site URL that you will be connecting to, this will be the same as the Site you enter when logging into the desktop application, or the same as the URL you enter in a browser to connect to the web portal.

### PSA Directory
_Required_
The directory that PSA is installed in. According to the ConnectWise 'Calling the Web Service' article, this should almost always be the v4\_6\_release.

### Use SSL
_Required_
If the site you are connecting to uses a secure connection (HTTPS) then check this box, otherwise leave unchecked.


## ConnectWise Security Roles


The Username provided must be a ConnectWise Member that is part of a Security Role with the appropriate access to the Accounting Interface in the Finance Module. The documentation associated with each of the tasks describes what level of access is required:



[![ConnectWise Accounting Interface Connection Security Module](http://www.zynk.com/images/v2/connectwise/cw-accounting-interface-connection-access.png)](http://www.zynk.com/images/v2/connectwise/cw-accounting-interface-connection-access.png)

