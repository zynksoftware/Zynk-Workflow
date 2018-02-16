---
slug: connecting-to-a-pop3-server
redirect_from: "/article/602-connecting-to-a-pop3-server"
title: Connecting to a POP3 Server
---
Some of the tasks in the Email Connector require a POP3 connection, so you will need to create a connection with the type 'POP3'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your POP3 details:

[![POP3 Connection](http://www.zynk.com/images/v2/pop3_connection.png)](http://www.zynk.com/images/v2/pop3_connection.png)

Enter your POP3 details as described below, then click 'Finish' to create the connection.

## Settings
### Authentication Method
_Required_  
Select the authentication method to use when authenticating with the POP3 server. The available options are:  

 * **Auto** - This is the recommended setting. It will use APOP if it's supported by the server, or will fall back to Username/Password if not.
 * **APOP** - Authenticate using the more secure Authenticated Post Office Protocol method. This method is not supported by some POP3 servers.
 * **UsernameAndPassword** - Authenticate using the Username/Password method. Not recommended if 'Use SSL' is set to false.
 * **CramMD5** - Authenticate using the CRAM-MD5 method.

### Password
_Optional_  
Enter the password, if required to authenticate you to receive emails.

### Port
_Required_  
The port number to use for POP access e.g. 995 for SSL connections or 110 for non-secure connections.

### Server
_Required_  
The URL or IP address of your POP3 Mail server e.g. pop.gmail.com or if using an internal mail server e.g. 192.168.1.1

### Use SSL
_Required_  
Set this to True if your POP3 server requires an SSL connection.

### Username
_Required_  
Enter the username used to access your account to receive emails.