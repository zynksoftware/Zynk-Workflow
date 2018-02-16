---
slug: connecting-to-connectwise
redirect_from: "/article/925-connecting-to-connectwise"
title: Connecting to ConnectWise
---


All of the tasks in the ConnectWise connector require a connection to ConnectWise. The type of connection required depends on the task being used. The ConnectWise Download Agreements, Download Companies, Download Invoices, Download Opportunities, Download Purchase Orders, List Reports and Run Report Tasks use the 'ConnectWise' connection type, so you will need to create a connection with this type when using those tasks. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below:



[![ConnectWise Connection](http://www.zynk.com/images/v2/connectwise/connection.png)](http://www.zynk.com/images/v2/connectwise/connection.png)



Enter your ConnectWise details as described below, then click 'Finish' to create the connection.

## Settings

### PSA Site
_Required_
The ConnectWise Site URL that you will be connecting to, this will be the same as the Site you enter when logging into the desktop application, or the same as the URL you enter in a browser to connect to the web portal.

### Company
_Required_
The name of the ConnectWise Company you are connecting to, this will be the same as the Company you enter when logging into the desktop application or web portal.

### Username 
_Required_
The name of the ConnectWise Integrator Login you will be using to access the ConnectWise SOAP API. See the section below on Configuring ConnectWise Integrator Logins if you are unsure of how access to the SOAP API's is managed.

### Password
_Required_
The password of the ConnectWise Integrator Login.


## Configuring ConnectWise Integrator Logins


The Integrator Logins can be configured from the Integrator Login Table in the Setup Tables found under the System category in ConnectWise.



[![ConnectWise Setup Tables Integrator Login](http://www.zynk.com/images/v2/connectwise/cw-setup-tables-integrator-login.png)](http://www.zynk.com/images/v2/connectwise/cw-setup-tables-integrator-login.png)



You will need to allow the Integrator Login you are using access to the relevant API's depending on the tasks you would like to use in Zynk. For example, you would need to enable the Opportunity API if you would to use the Download Opportunities Task in Zynk. You can check the documentation associated with each task to find out the required API access.



[![ConnectWise Setup Tables Integrator Login API Access](http://www.zynk.com/images/v2/connectwise/cw-setup-tables-integrator-login-api-access.png)](http://www.zynk.com/images/v2/connectwise/cw-setup-tables-integrator-login-api-access.png)

