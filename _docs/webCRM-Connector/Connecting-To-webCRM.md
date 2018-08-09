---
slug: connecting-to-webcrm
title: Connecting to webCRM
---
All of the tasks in the [webCRM](webcrm) connector require a connection to your webCRM account, so you will need to create a connection with the type 'webCRM'.  See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your webCRM details: 

![webCRM Connection](/assets/images/webcrm/webcrm_connection.png)

Enter your webCRM details as described below, then click 'Finish' to create the connection.  Zynk will attempt to login in to webCRM with the provided details to verify the token.

## Settings
### Application Token
_Required_
You will need to generate an application token from you webCRM account - Configuration -> Integration -> API.  When creating an application you will have to provide permissions per area.  For Zynk to work you will have to provide `Read only` as a minimum for Export tasks, and `Read/Write` for Imports - if the correction permissions are not set Zynk will not be able to run as intended.