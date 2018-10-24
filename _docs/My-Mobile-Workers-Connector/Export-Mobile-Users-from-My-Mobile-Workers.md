---
slug: export-mobile-users-from-my-mobile-workers
title: Export Mobile Users from My Mobile Workers
---
The My Mobile Workers platform will allow users to be created. These users will be allowed to access the mobile app to log job and invoice information remotely. For example, a trades person will be able to log into the app and provide information on recent jobs they've completed so their time can be accounted for internally in the company.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Get_Mobile_Users).

This task will export all available mobile users from My Mobile Workers in an XML format.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

## XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <MobileUsers>
    <MobileUser>
      <username>ChrisBaker1</username>
      <email>chris.baker@zynk.com</email>
      <color>7D8E60</color>
    </MobileUser>
    <MobileUser>
      <username>zynktester</username>
      <email />
      <color>000aff</color>
    </MobileUser>
  </MobileUsers>
</MyMobileWorkersData>
```
