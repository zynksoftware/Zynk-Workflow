---
slug: export-routes-from-my-mobile-workers
title: Export Routes from My Mobile Workers
---
The My Mobile Workers platform will allow routes to be created. The routes are created by the company to allow remote mobile app users select jobs based on the fastest routes. For example, trades people can organise their day by using the most fuel efficient routes around their designated jobs.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Get_all_routes).

This task will export all available routes from My Mobile Workers in an XML format.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

## XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Routes>
    <Route>
      <external_id>54</external_id>
      <route_code>g</route_code>
      <route_name>rhgi</route_name>
    </Route>
  </Routes>
</MyMobileWorkersData>
```
