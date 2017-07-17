---
slug: connecting-to-quickbooks-online
redirect_from: "/article/865-connecting-to-quickbooks-online"
title: Connecting to QuickBooks Online
---


All of the tasks in the Quickbooks Online connector require a connection to a Quickbooks Online company, so you will need to create a connection with the type 'Quickbooks Online'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your Quickbooks Online details:



[![Quickbooks Online Connection](http://www.zynk.com/images/v2/quickbooks_online_connection.png)](http://www.zynk.com/images/v2/quickbooks_online_connection.png)



Enter your Quickbooks Online details as described below, then click 'Finish' to create the connection.

## Settings

### Environment
_Required_  
Select the environment your Quickbooks Online company is in. The available options are:	  

- Live - Choose this option to connect to a live Quickbooks company.
- Sandbox - Choose this option to connect to a sandbox Quickbooks company.

### Auth Token
_Required_  
Click the 'Sign In' button to generate an auth token.

### Expiry Date
_Read Only_  
Once you have generated an auth token, it's expiry date will be shown here. When the connection is in use, Zynk will automatically renew the auth token when approaching the expiry date. You can replace expired auth tokens manually by signing in to Quickbooks again.
