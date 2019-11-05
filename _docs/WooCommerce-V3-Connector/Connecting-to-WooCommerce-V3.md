---
slug: connecting-to-woocommerce-v3
title: Connecting to WooCommerce V3.0+
---
All of the tasks in the WooCommerce V3.0+ connector require a connection to WooCommerce, so you will need to create a connection with the type 'WooCommerce Version 3.0+'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your WooCommerce details: 

![WooCommerce Connection](/assets/images/woocommerce-v3/woocomerce-v3-connection.png)

Enter your WooCommerce details as described below, then click 'Finish' to create the connection. For more information on generating API keys see [WooCommerce REST API](https://docs.woocommerce.com/document/woocommerce-rest-api/).

## Settings
### URL
_Required_  
Enter any URL for your WooCommerce store (e.g. the homepage).

### Consumer Key
_Required_  
Enter your WooCommerce API Consumer Key. This can be generated from your site's admin, under Users > Your Profile > WooCommerce API Keys.

### Consumer Secret
_Required_  
Enter your WooCommerce API Consumer Secret. This can be generated from your site's admin, under Users > Your Profile > WooCommerce API Keys.

### Authentication Method
_Required_  
Choose which authentication method to use.
- **QueryString** - This option will send your authentication details to WooCommerce as part of the query string on each API request. Use this option if your server is unable to parse the authorization header correctly.
- **AuthorizationHeader** - This option will send your authentication details to WooCommerce as part of the authorization header on each API request. If you are using this method over HTTPS, and see a "Consumer key is missing" error, use the QueryString option instead.
