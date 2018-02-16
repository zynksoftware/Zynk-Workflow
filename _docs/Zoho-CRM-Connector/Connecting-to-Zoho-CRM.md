---
slug: connecting-to-zoho-crm
redirect_from: "/article/651-connecting-to-zoho-crm"
title: Connecting to Zoho CRM
---
All of the tasks in the Zoho CRM connector require a connection to Zoho CRM, so you will need to create a connection with the type 'Zoho CRM'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your Zoho CRM details:

[![Zoho CRM Connection](http://www.zynk.com/images/v2/zoho_crm_connection.png)](http://www.zynk.com/images/v2/zoho_crm_connection.png)

Enter your Zoho CRM details as described below, then click 'Finish' to create the connection.

## Settings
### Login
_Required_  
Select the login method you use to sign in to Zoho CRM.

### Email
_Dependant_  
If you log in using the standard login method, enter the email address you use to login to your Zoho CRM account here.

### Password
_Dependant_  
If you log in using the standard login method, enter the password you use to login to your Zoho CRM account here.

### Application Name
_Dependant_  
If you log in using the standard login method, enter an application name here. This is used within Zoho CRM to identify the application the token belongs to. You can enter anything in this box, such as 'Zynk'.

### Token
_Required_  
If you log in using the standard login method, click the 'Request Token' button get a token from Zoho CRM, once you have entered all of the details above.	  
  
If you log in using the two factor authentication method, you will need to generate a token yourself and paste it into this box. You can generate a token in Zoho CRM by going to Setup > Developer Space > CRM API.