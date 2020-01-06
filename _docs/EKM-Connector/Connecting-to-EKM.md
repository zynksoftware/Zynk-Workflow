---
slug: connecting-to-ekm
title: Connecting to EKM
---
All of the tasks in the EKM connector require a connection to EKM, so you will need to create a connection with the type 'EKM'. See [Connection Manager](connection-manager) for instructions on creating a new connection. You will see a screen like the one below, requesting your EKM details:

![EKM Connection](/assets/images/ekm/ekm-connection.png)

Enter your EKM details as described below, then click 'Finish' to create the connection.

## Settings
### Refresh Token
_Required_  
Click the 'Generate' button to create a refresh token. This will bring up a new window where you can log in to your EKM account, and grant Zynk access to your data. Once you have done this, a token will be automatically generated.

Please note that if a new refresh token is generated for an EKM store, it will invalidate the old one. This will cause an 'invalid grant' error if you try to connect using the old refresh token. To avoid this issue, we recommend that only one connection is created per EKM store.

### Expires
_Required_  
Once you have generated a refresh token, the date and time it will expire will be shown here. The expiry date will be automatically extended when the connection is used. So long as the connection is used regularly, it will never expire.

If you try to use the connection after it has expired, you will receive an error. This can be resolved by generating a new refresh token, as described above.
