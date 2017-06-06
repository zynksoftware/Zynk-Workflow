---
slug: get-page
redirect_from: "/article/894-get-page"
title: Get Page
---
This task will retrieve the page information of either your own page or another based on your settings.

## Settings
### Output File
_Required_  
The file which your page information will be saved to.

### Page
_Optional_  
Leave blank for your own page, otherwise specify the page name you wish to download.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
```xml
<?xml version="1.0" encoding="utf-8"?>
<page>
  <data>
    <id>10153366940268781</id>
    <first_name>Joseph</first_name>
    <gender>male</gender>
    <last_name>Harrison</last_name>
    <link>https://www.facebook.com/app_scoped_user_id/10151234940268781/</link>
    <locale>en_US</locale>
    <name>Joseph Harrison</name>
    <timezone>1</timezone>
    <updated_time>2016-07-21T12:46:05+01:00</updated_time>
    <verified>true</verified>
  </data>
</page>
```