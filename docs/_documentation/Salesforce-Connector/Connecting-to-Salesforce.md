---
slug: connecting-to-salesforce
redirect_from: "/article/606-connecting-to-salesforce"
title: Connecting to Salesforce
---

All of the tasks in the Salesforce connector require a connection to Salesforce. The type of connection required depends on the task being used. The Salesforce Create, Delete, Query, Update and Upsert Tasks use the 'Salesforce' connection type, so you will need to create aconnection with this type when using those tasks. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your Salesforce details:

[![Salesforce Connection](http://www.zynk.com/images/v2/salesforce_connection_1.png)](http://www.zynk.com/images/v2/salesforce_connection_1.png)

Enter your Salesforce details as described below, then click 'Finish' to create the connection.

## Settings
### Environment
_Required_  
Select the Salesforce environment to connect to.

 * **Live** - Connect to a live Salesforce organization. 
 * **Sandbox** - Connect to a test Salesforce organization. We recommend using this option when developing and testing your integration. Access to a sandbox depends on your Salesforce edition.

### API Version
_Required_  
Select the Salesforce API version to use. This can usually be left set to the default value of 20.0, but can be changed if you need access to fields only supported by newer versions of the API.

### Sign In
_Required_  
Click the sign in button to log in to your Salesforce organization. A browser window like the one shown below will appear asking you to login in and approve access for Zynk.
  
[![Salesforce Connection](http://www.zynk.com/images/v2/salesforce_connection_2.png)](http://www.zynk.com/images/v2/salesforce_connection_2.png)  
  
Once you have logged in, click on the 'Approve' button to grant Zynk access your Salesforce organization. Upon doing this, Salesforce will send an access token to Zynk which will be stored in the connection.

## Removing Access to Salesforce
If you ever need to reset the access between Zynk and Salesforce, click into Setup > Administration Setup > Manage Users and click on the User, scroll down to Remote Access, look for Zynk in the Application name and click on the Revoke button on the left.