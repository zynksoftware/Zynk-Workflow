---
slug: connecting-to-xero-with-oauth-2
title: Connecting to Xero
---

All of the tasks in the Xero connector require a connection to Xero, so you will need to create a connection with the type 'Xero (Private API, OAuth 2.0)'. See [Managing Connections](managing-connections) for instructions on creating a new connection.

Zynk connects to Xero using the private API, which requires you to set up a private application in Xero. See below for instructions on how to do this

## Xero Private App Creation process

1. Login in to your developer account at https://developer.xero.com/myapps/

2. Click "New App" at the top right.

![Xero](/assets/images/xero/xero_oauth_2_private_app.png)

3. Enter a name for the application. This can be anything you like, such as 'Zynk Integration'.

4. For the 'Company or application URL', enter https://zynk.com/

5. Leave the 'Privacy policy URL' empty.

6. For the 'OAuth 2.0 redirect URI', enter https://zynk.com/

7. Click the 'Create app' button.

![Xero](/assets/images/xero/xero_oauth_2_private_app_2.png)

8. Click the Generate secret link. The generated client ID and secret will need to be copied to your Zynk connection.

Futher information can be found in Xero's [Private Application Documentation](https://developer.xero.com/documentation/auth-and-limits/private-applications/).

## Zynk Connection

When creating a 'Xero (Private API, OAuth 2.0)' connection in Zynk, you will see a screen like the one below, requesting your Xero private application details:

![Xero](/assets/images/xero/xero_oauth_2_connection.png)

### Client ID
_Required_  
Enter the client ID that Xero has generated for your private app.

### Client Secret
_Required_  
Enter the client secret that Xero has generated for your private app.

### Refresh Token
_Required_  
Click the Generate button, then log into Xero and approve access for Zynk.

### Organisation
_Required_  
After you've generated a refresh token, this list will display all the organisations your private app has access to. Select the organisation you want to connect to. 

If you want to connect to multiple organisations, you will need to create a separate connection in Zynk for each one. When doing this, you can reuse the same private app by copying the client ID and secret you have already generated.