---
slug: exporting-pages-from-wordpress
redirect_from: "/article/914-downloading-pages-from-wordpress"
title: Exporting Pages From WordPress
---


This task will export pages from WordPress in an XML format. The results can be filtered if required. See below for a sample output file.


## Settings

### Connection 
_Required_
The WordPress connection use when running the Export Pages task.

### Output File
_Required_
The file to save results from the Export Pages task. The results are returned as an array of the Page object as detailed in the example below.

### WooCommerce Export Settings
See [Common WordPress Settings](common-wordpress-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


A sample output file is shown below.


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfPage xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <Page>
        <id>2</id>
        <external_id>12345</external_id>
        <date>2015-09-08T13:42:17</date>
        <date_gmt>2015-09-08T12:42:17</date_gmt>
        <guid>
          <rendered>http://localhost:8080/wordpress/?page_id=2</rendered>
        </guid>
        <link>https://localhost/wordpress/sample-page/</link>
        <modified>2016-09-05T10:39:16</modified>
        <modified_gmt>2016-09-05T09:39:16</modified_gmt>
        <slug>sample-page</slug>
        <type>page</type>
        <title>
          <rendered>Sample Page</rendered>
        </title>
        <author>
          <id>1</id>
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
        </author>
        <excerpt>
          <rendered><p>This is an example page. It&amp;#8217;s different from a blog post because it will stay in one place and will show up in your site navigation (in most themes). Most people start with an About page that introduces them to potential site visitors. It might say something like this: Hi there! I&amp;#8217;m a bike messenger &amp;hellip; <a href="https://localhost/wordpress/sample-page/" class="more-link">Continue reading <span class="screen-reader-text">Sample Page</span></a></p></rendered>
        </excerpt>
        <featured_media>0</featured_media>
        <comment_status>open</comment_status>
        <ping_status>open</ping_status>
        <menu_order>0</menu_order>
        <template />
      </Page>
    </ArrayOfPage>
```