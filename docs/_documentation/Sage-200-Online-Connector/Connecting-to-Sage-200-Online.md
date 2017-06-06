---
slug: connecting-to-sage-200-online
redirect_from: "/article/827-connecting-to-sage-200-online"
title: Connecting to Sage 200 Online
---
All of the tasks in the Sage 200 Online connector require a connection to a Sage 200 Online company, so you will need to create a connection with the type 'Sage 200 Online'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your Sage 200 Online details:

![Sage 200 Online Connection](http://www.zynk.com/images/v2/sage_200_online_connection.png)

Enter your Sage 200 details as described below, then click 'Finish' to create the connection.

## Settings
### Access Token
_Required_  
You can generate an access token for Sage 200 Online by following the steps below. This allows Zynk to access your Sage data.

1. Click the 'Login' button, which will take you to the Sage ID login page.
2. Enter your Sage ID username and password, then click 'Sign In'.
3. Sage will ask you to confirm whether you give Zynk permission to access your data, click 'Allow' to generate the access token.

### Company
_Required_  
Once you have an access token, the companies you have access to will be listed here. Select the one you want Zynk to connect to. You can update the company list by clicking the 'Refresh' button.

## Access Token Expiry
Sage 200 Online only allows access for a period of 6 months at a time. Once this has elapsed, you will see an error when Zynk tries to connect to Sage 200 Online, stating that the access token has expired. When this happens, simply edit your existing Sage 200 Online connection, and repeat the steps above to generate a new access token.