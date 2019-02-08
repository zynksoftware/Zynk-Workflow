---
slug: connecting-to-bigcommerce-v3
title: Connecting to BigCommerce V3
---
All of the tasks in the BigCommerce V3 connector require a connection to BigCommerce, so you will need to create a connection with the type 'BigCommerce V3'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your BigCommerce details.

From within your BigCommerce store you will need to create an API Account, this is documented on the [BigCommerce Dev Center](https://developer.bigcommerce.com/api-docs/getting-started/basics/authentication#authentication_getting-api-credentials). 

![BigCommerce V3 Connection](http://www.zynk.com/images/v2/big_commerce_v3_connection.png)

Enter your BigCommerce details as described below, then click 'Finish' to create the connection.

## Settings
### Store Hash
_Required_  
The store hash is used to build up the connection to your site, and is shown when creating the API Account. As an example, if your Base API Path is `https://api.bigcommerce.com/stores/123456/` you would enter `123456` as the store hash. 

### Client ID
_Required_  
The client id is shown after you have created the API Account from your store admin.  This value is only shown once, so make sure you keep a secure record or you may have to create a new account.

### Access Token
_Required_  
The access token is shown after you have created the API Account from your store admin.  This value is only shown once, so make sure you keep a secure record or you may have to create a new account.