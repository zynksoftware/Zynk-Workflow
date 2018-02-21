---
slug: connecting-to-peoplevox
title: Connecting to Peoplevox
---

All of the tasks in the [Peoplevox](peoplevox) connector require a connection to a Peoplevox instance, so you will need to create a connection with the type 'Peoplevox'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your Peoplevox details:

![Connecting to Peoplevox](/assets/images/peoplevox/peoplevox-connection.png)

Enter your Peoplevox details as described below, then click 'Finish' to create the connection.  Zynk will validate the details provided by attempting to authenticate with Peoplevox.

You create the username and password in the Web application for your WM System, in the Setup page, and Users Tab.

## Settings
### Client ID
_Required_  
Enter the unique identifier for the instance of Peoplevox you are wanting to connect to.

### Username
_Required_  
Enter the username for the login you want to use for the integration.

### Password
_Required_  
Enter the password for the login you want to use for the integration.

### Website
_Required_  
Enter the url to your Peoplevox instance.  For hosted services the URL is wms.peoplevox.net/ClientId.  An example for the URL could be: http://wms.peoplevox.net/myclientid/resources/integrationservicev4.asmx
