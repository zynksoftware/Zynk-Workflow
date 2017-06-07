---
slug: connecting-to-amazon-vendor-central
redirect_from: "/article/660-connecting-to-amazon-vendor-central"
title: Connecting to Amazon Vendor Central
---
All of the tasks in the [Amazon Vendor Central]] Connector require a connection to Amazon's upload or download SFTP location. You will need to create a connection with the type 'Amazon Vendor Central Download' or 'Amazon Vendor Central Upload', depending on which task you are using. See [Connection Manager](connection-manager) for instructions on creating a new connection. You will see a screen like the one below regardless of which of the two connection types was selected, requesting your SFTP details:

[![Amazon Vendor Central Connection](http://www.zynk.com/images/v2/amazon_vendor_central_connection.png)](http://www.zynk.com/images/v2/amazon_vendor_central_connection.png)

Enter the SFTP details Amazon provided during the Basic Setup process as described below, then click 'Finish' to create the connection. Note that Amazon will provide you with a set of 4 SFTP accounts, for uploading and downloading both test and live data. You can enter the details for each one by repeating this process.

## Settings
### Username
_Required_  
The SFTP username provided by Amazon.

### Private Key File
_Required_  
You will also have generated a public/private key pair using a tool (such as puttygen). Save the private key which corresponds to the public key you provided to Amazon, and enter the file path here.

### Passphrase
_Optional_  
If you have password protected the private key file, enter the password here.

###Directory
_Required_  
The SFTP directory to upload/download files from. You will have chosen this as part of the EDI Self Service setup process. This is set to Amazon's default directory when you first create the connection. 