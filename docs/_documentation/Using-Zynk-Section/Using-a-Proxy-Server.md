---
slug: using-a-proxy-server
redirect_from: "/article/74-using-a-proxy-server"
title: Using a Proxy Server
---
You can specify a proxy server at each individual task level, however, if always use a proxy server to access the internet you can set up 4 Global Variables which will be used as the defaults for any tasks that need to access the Internet.

Click on the Global Variables button on the Main Toolbar

 * Setup a variable called **PROXY_ADDRESS** and set this to e.g. 192.168.1.100
 * Setup a variable called **PROXY_USERNAME** and set this to the username if required to access your proxy server e.g. PaulJohnson
 * Setup a variable called **PROXY_PASSWORD** and set this to the username if required to access your proxy server e.g. supersecret
 * Setup a variable called **PROXY_PORT** and set this to the Proxy server port number e.g. 8080

Note the variables are case sensitive and must be all UPPERCASE