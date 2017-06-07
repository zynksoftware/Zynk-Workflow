---
slug: connecting-to-an-smtp-server
redirect_from: "/article/601-connecting-to-an-smtp-server"
title: Connecting to an SMTP Server
---
## Connecting to an SMTP Server
Some of the tasks in the Email Connector require a SMTP connection, so you will need to create a connection with the type 'SMTP Server'. See [Connection Manager](connection-manager) for instructions on creating a new connection. You will see a screen like the one below, requesting your SMTP details:

[![SMTP Connection](http://www.zynk.com/images/v2/smtp_connection.png)](http://www.zynk.com/images/v2/smtp_connection.png)

Enter your SMTP details as described below, then click 'Finish' to create the connection.

## Settings
### SMTP Password
_Optional_  
Enter the password, if required to authenticate you to send email.

### SMTP Port
_Required_  
The port number to use for sending email e.g. 25 for non secure, 587 or 993 for secure (Gmail uses 587).

### SMTP Server
_Required_  
The address of the SMTP server (Gmail is smtp.gmail.com).

### SMTP Username
_Required_  
Enter the username to access your account to send email.

### Timeout
_Required_  
The length of time in milliseconds to wait whilst trying to send the email. Defaults to 6000 (6 seconds).

### Use SSL
_Required_  
Set this to True if your SMTP server requires an SSL connection.