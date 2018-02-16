---
slug: connecting-to-an-ftp-server
redirect_from: "/article/603-connecting-to-an-ftp-server"
title: Connecting to an FTP Server
---
## Connecting to a FTP Server
All of the tasks in the [FTP]] Connector require an FTP connection, so you will need to create a connection with the type 'FTP'. See [Connection Manager](connection-manager) for instructions on creating a new connection. You will see a screen like the one below, requesting your FTP server details:

[![FTP Connection](http://www.zynk.com/images/v2/ftp_connection.png)](http://www.zynk.com/images/v2/ftp_connection.png)

Enter you FTP details as described below, then click 'Finish' to create the connection.

## Settings
### Password
_Optional_  
FTP server password.

### Server
_Required_  
URL or IP address of FTP server. Must begin with ftp://

### Use Binary
_Required_  
Set to false to transfer files to the FTP server in ASCII text mode.

### Use Passive
_Required_  
Set to true if passive mode should be used when connecting to the server.

### Use SSL
_Required_  
Set to true to connect to the FTP server securely.

### Username
_Required_  
Username used to login to FTP server.