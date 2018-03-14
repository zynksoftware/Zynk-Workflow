---
slug: exporting-users-from-wordpress
redirect_from: "/article/916-downloading-users-from-wordpress"
title: Exporting Users From WordPress
---


This task will export users from WordPress in an XML format. The results can be filtered if required. See below for a sample output file.

### Connection 
_Required_
The WordPress connection use when running the Export Users task.

### Output File
_Required_
The file to save results from the Export Users task. The results are returned as an array of the User object as detailed in the example below.

### WooCommerce Export Settings
See [Common WordPress Settings](common-wordpress-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


A sample output file is shown below.


```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfUser xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <User>
    <id>1</id>
    <external_id>12345</external_id>
    <name>admin</name>
    <url />
    <description />
    <link>https://localhost/wordpress/author/admin/</link>
    <slug>admin</slug>
    <registered_date xsi:nil="true" />
    <avatar_urls>
      <item>
        <key>24</key>
        <value>https://secure.gravatar.com/avatar/02f0389f39fb5b37a548110c961725a1?s=24&amp;d=mm&amp;r=g</value>
      </item>
      <item>
        <key>48</key>
        <value>https://secure.gravatar.com/avatar/02f0389f39fb5b37a548110c961725a1?s=48&amp;d=mm&amp;r=g</value>
      </item>
      <item>
        <key>96</key>
        <value>https://secure.gravatar.com/avatar/02f0389f39fb5b37a548110c961725a1?s=96&amp;d=mm&amp;r=g</value>
      </item>
    </avatar_urls>
  </User>
</ArrayOfUser>
```
