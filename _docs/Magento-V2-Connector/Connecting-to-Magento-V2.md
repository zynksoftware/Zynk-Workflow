---
slug: connecting-to-magento-v2
redirect_from: "/article/764-connecting-to-magento"
title: Connecting to Magento V2
---
All of the tasks in the Magento V2 connector require a connection to Magento, so you will need to create a connection with the type 'Magento V2'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below.

![Magento V2 Connection](http://www.zynk.com/images/v2/magento_v2_connection.png)

Enter your Magento details as described below, then click 'Finish' to create the connection.

## Settings
### URL
_Required_  
Enter the URL for your Magento website (e.g. http://www.mymagentosite.com/).

### Username
_Required_  
Enter the username you use to sign in to the administration section of the website. This is not stored by Zynk, and is only used to generate the token.

### Password
_Required_  
Enter the password you use to sign in to the administration section of the website. This is not stored by Zynk, and is only used to generate the token.

### Token
_Required_  
Click the 'Generate' button to generate an 'Admin' API token. Alternatively, an 'Integration' token can be generated within Magento V2 by navigating to System > Integrations -> Add New Integration. Once an integration token has been generated, the 'Access Token' value can be used for the token Magento V2 connection.

The _primary_ difference between the token types is the default lifetime. For further information, refer to the [Magento DevDocs - Token-based authentication](https://devdocs.magento.com/guides/v2.3/get-started/authentication/gs-authentication-token.html) article.

### HTTP Auth Username
_Optional_  
If your Magento website uses HTTP basic authentication, enter the username here.

### HTTP Auth Password
_Optional_  
If your Magento website uses HTTP basic authentication, enter the password here.

### Keep Alive
_Optional_  
Tick this box to set the keep alive header in all HTTP requests to the Magento API. 
