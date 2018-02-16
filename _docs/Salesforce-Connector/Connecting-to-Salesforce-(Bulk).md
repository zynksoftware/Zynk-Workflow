---
slug: connecting-to-salesforce-bulk
redirect_from: "/article/607-connecting-to-salesforce-bulk"
title: Connecting to Salesforce (Bulk)
---
All of the tasks in the Salesforce connector require a connection to Salesforce. The type of connection required depends on the task being used. The Bulk Salesforce Operation, Upload Products and Upload Records Tasks use the 'Salesforce (Bulk)' connection type, so you will need to create a connection of this type when using those tasks. See [Connection Manager](connection-manager) for instructions on creating a new connection. You will see a screen like the one below, requesting your Salesforce details:

[![Salesforce Bulk Connection](http://www.zynk.com/images/v2/salesforce_bulk_connection.png)](http://www.zynk.com/images/v2/salesforce_bulk_connection.png)

Enter your Salesforce details as described below, then click 'Finish' to create the connection.

## Settings

### Username
_Required_  
Enter your salesforce username

### Password
_Required_  
Enter your salesforce password

### Token
_Required_  
Enter your salesforce security token. If you don't already have a security token, you can obtain one from Salesforce by going to Setup > My Personal Information > Reset My Security Token.

### Environment
_Required_  
Select the Salesforce environment to connect to.	  

### API Version
_Required_  
Select the Salesforce API version to use. This can usually be left set  to the default value of 21.0, but can be changed if you need access to  fields only supported by newer versions of the API.

## Removing Access to Salesforce
If you ever need to reset the access between Zynk and Salesforce, click into Setup > Administration Setup > Manage Users and click on the User, scroll down to Remote Access, look for Zynk in the Application name and click on the Revoke button on the left.