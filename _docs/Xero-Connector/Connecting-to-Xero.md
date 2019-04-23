---
slug: connecting-to-xero
redirect_from: "/article/667-connecting-to-xero"
title: Connecting to Xero
---

All of the tasks in the Xero connector require a connection to Xero, so you will need to create a connection with the type 'Xero'. See [Managing Connections](managing-connections) for instructions on creating a new connection.

Zynk connects to Xero using the private API, which requires you to set up a private application in Xero. Xero provide instructions on how to do this in the documentation section of their site under [Private Applications](https://developer.xero.com/documentation/auth-and-limits/private-applications/). Note that the name for the private application is not important, so you can choose anything (such as 'Zynk Integration').

In Zynk you will see a screen like the one below, requesting your Xero private application details:

![Xero](/assets/images/xero/xero_connection.png)

### Xero Private App Creation process

1. Click on generate to generate a new pair of public and private key files, setting the password for these files when prompted.

2. Login in to your developer account at https://developer.xero.com/myapps/

![Xero](/assets/images/xero/xeroapp.png)

3. Select "New App" at the top right.

4. Select "Private App" on the new window.

5. Enter a name for the application, which can be anything and select the company in Xero you wish Zynk to access.

6. Click on the prompt and naviaget and select the publick key file (ending in .cer).

7. Click on create app.

8. You will be presented with a page containing a Consumer Key for the new app, enter this in the Consumer Key section back in the Zynk Connection Wizard.

9. Ensure the correct private key file (ending in .pfx) is displayed in the Certificate File section of Zynk then selection Finish.


## Settings

### Consumer Key
_Required_  
Enter the consumer key that Xero has generated for your private app.

### Certificate File 
_Required_  
If you generated your own certificate when setting up your private application in Xero, click the 'Browse' button, and select the certificate (.pfx) file you generated. Alternatively, Zynk can generate a certificate for you by clicking the 'Generate' button. Simply enter a file name when prompted and optionally enter a password to protect the certificate with. You will need to upload the generated .cer file to your Xero private application.

### Certificate Password
_Required_  
If you chose to password protect the certificate file, enter the password here.

