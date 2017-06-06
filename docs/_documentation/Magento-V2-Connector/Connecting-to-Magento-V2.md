---
slug: connecting-to-magento-v2
redirect_from: "/article/764-connecting-to-magento"
title: Connecting to Magento V2
---
All of the tasks in the Magento V2 connector require a connection to Magento, so you will need to create a connection with the type 'Magento V2'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below.

![Magento V2 Connection](http://www.zynk.com/images/v2/magento_v2_connection.png)

Enter your Magento details as described below, then click 'Finish' to create the connection.

## Settings
###URL
_Required_  
Enter the URL for your Magento website (e.g. http://www.mymagentosite.com/).

###Username
_Required_  
Enter the username you use to sign in to the administration section of the website. This is not stored by Zynk, and is only used to generate the token.

###Password
_Required_  
Enter the password you use to sign in to the administration section of the website. This is not stored by Zynk, and is only used to generate the token.

###Token
_Required_  
Click the 'Generate' button to generate an API token.

###HTTP Auth Username
_Optional_  
If your Magento website uses HTTP basic authentication, enter the username here.

###HTTP Auth Password
_Optional_  
If your Magento website uses HTTP basic authentication, enter the password here.

###Keep Alive
_Optional_  
Tick this box to set the keep alive header in all HTTP requests to the Magento API. 