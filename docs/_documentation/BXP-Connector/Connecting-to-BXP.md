---
slug: connecting-to-bxp
redirect_from: "/article/971-connecting-to-bxp"
title: Connecting to BXP
---


All of the tasks in the BXP connector require a connection to a Sage 50 company, so you will need to create a connection with the type 'BXP'. See [Managing Connections](managing-connections) for instructions on creating a new connection. You will see a screen like the one below, requesting your BXP details:



[![BXP Connection](http://www.zynk.com/images/v2/bxp_connection.png)](http://www.zynk.com/images/v2/bxp_connection.png)



Enter your BXP details as described below, then click 'Finish' to create the connection.

## Settings

### Client 
_Required_
Enter your BXP client name. This is provided by BXP, and can be seen in the URL of any page you view whilst signed in to the BXP system (e.g. https://ww3.allnone.ie/client/	*<Your Client Name>*/main/main.asp).

### User ID
_Required_
Enter the User ID to sign in to the BXP API as. It it recommended that you set up a new user as follows:	  

1. Create a user but give the user no functional access to BXP
2. Apply IP address restrictions to the account, so it can only be used from controlled environments
3. Grant the user explicit access to the secure form data
4. Explicitly allow the form data to be externally accessible

### User Key
_Required_
Enter the key for your chosen user ID.