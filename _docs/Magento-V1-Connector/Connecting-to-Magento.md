---
slug: connecting-to-magento
redirect_from: "/article/668-connecting-to-magento"
title: Connecting to Magento
---
All of the tasks in the Magento connector require a connection to Magento, so you will need to create a connection with the type 'Magento'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below.

Zynk requires an API user account to be able to connect to Magento. You can create one from your Magento admin by going to System -> Web Services -> SOAP/XML-RPC Users. Make sure you assign the user a role which grants it access to the areas of Magento you want to integrate with. Roles can be configured from System -> Web Services -> SOAP/XML-RPC Roles.

![Magento Connection](http://www.zynk.com/images/v2/magento_connection.png)

Enter your Magento details as described below, then click 'Finish' to create the connection.

## Settings
### URL
_Required_  
Enter your API URL (e.g. https://example.com/api/xmlrpc/, replacing example.com with your domain).

### User
_Required_  
Your API username, as configured within SOAP/XML-RPC Users in Magento.

### Password
_Required_  
Your API password, as configured within SOAP/XML-RPC Users in Magento.

### HTTP Auth User
_Optional_  
If your Magento website uses HTTP basic authentication, enter the username here.

### HTTP Auth Password
_Optional_  
If your Magento website uses HTTP basic authentication, enter the password here.