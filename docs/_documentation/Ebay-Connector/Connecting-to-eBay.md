---
slug: connecting-to-ebay
redirect_from: "/article/665-connecting-to-ebay"
title: Connecting to eBay
---
All of the tasks in the eBay Connector require a connection to eBay, so you will need to create a connection with the type 'Ebay'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your eBay details:

![eBay Connection](http://www.zynk.com/images/v2/ebay_connection_1.png)

Enter your eBay details as described below, then click 'Finish' to create the connection.

## Settings
### Environment
_Required_  
Select the eBay environment to connect to.

* __Production__ - Connect to the live eBay system.
* __Sandbox__ - Connect to the eBay sandbox. Use this option when developing or testing an integration.

### Login
_Required_  
Click the 'Login' button to sign in to the selected eBay environment. A browser window will appear like the one shown below. Enter your email/user ID and password, and click 'Sign in'.

![eBay Sign In](http://www.zynk.com/images/v2/ebay_connection_2.png)

Once you have signed in successfully, eBay will send back an access token which will be stored in the connection. Please note that access tokens have an expiry date, so you will have to re-authenticate once it expires. You can check the expiry date at any time using the edit connection option.

