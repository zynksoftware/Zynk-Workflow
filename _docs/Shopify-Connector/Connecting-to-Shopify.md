---
slug: connecting-to-shopify
redirect_from: "/article/669-connecting-to-shopify"
title: Connecting to Shopify
---
All of the tasks in the Shopify connector require a connection to Shopify, so you will need to create a connection with the type 'Shopify'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your Shopify details:

![Shopify Connection](http://www.zynk.com/images/v2/shopify_connection.png)

Zynk connects to Shopify as a private app, so you will need to configure a private app on your Shopify store. Shopify provide [instructions](https://docs.shopify.com/api/authentication/creating-a-private-app) on how to this. Please note that the title of the private app is not important, so you can choose anything. Once you have set up the private app, enter your details into Zynk as described below, then click 'Finish' to create the connection.

## Settings
### Subdomain
_Required_  
Enter the subdomain from the admin URL of your store. For example, if your admin URL is `https://price-towne-and-kulas1234.myshopify.com`, your subdomain would be `price-towne-and-kulas1234`

### API Key
_Required_  
Enter the API key that Shopify generated for your private app.

### API Password
_Required_  
Enter the API password that Shopify generated for your private app. 