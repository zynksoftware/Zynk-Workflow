---
slug: connecting-to-an-sftp-server
redirect_from: "/article/604-connecting-to-an-sftp-server"
title: Connecting to an SFTP Server
---
## Connecting to an SFTP Server
All of the tasks in the SFTP Connector require an SFTP connection, so you will need to create a connection with the type 'SFTP'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your SFTP server details:

[![SFTP Connection](http://www.zynk.com/images/v2/sftp_connection.png)](http://www.zynk.com/images/v2/sftp_connection.png)

Enter you SFTP details as described below, then click 'Finish' to create the connection. Please note that when the workflow is connecting to an SFTP server, you may be prompted to allow the connection. In order to be able to run the workflow on a schedule, you must tick the option to always allow the connection, otherwise the connection to the server will be blocked.

## Settings
### Authentication Type
_Required_  
Select the authentication type to use when connection to the server. The available options are:	
 * Password - Log in to the SFTP using a username and password
 * Public Key - Log in to the SFTP using a username and public/private key pair

### Passphrase
_Optional_  
When using public key authentication and a password protected private key file, enter the private key file's password here.

### Password
_Optional_  
When using password authentication, enter the password used to login to the SFTP server.

### Port
_Required_  
The port number to use to connect to the SFTP server. The default is 22.

### Private Key File
_Optional_  
When using public key authentication, enter the private key file here. Note that this must be the private key, the public key should be stored in the SFTP server's settings. If you don't already have a public/private key pair, you can use a tool such as 	[PuttyGen](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) to generate them.

### Server
_Required_  
The URL or IP address of the SFTP Server, e.g. sftp.example.com

### Username
_Required_  
The username used to login to the SFTP server.