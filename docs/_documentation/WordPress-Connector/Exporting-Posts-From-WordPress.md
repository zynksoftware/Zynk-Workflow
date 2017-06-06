---
slug: exporting-posts-from-wordpress
redirect_from: "/article/915-downloading-posts-from-wordpress"
title: Exporting Posts From WordPress
---


This task will export posts from WordPress in an XML format. The results can be filtered if required. See below for a sample output file.

### Connection 
_Required_
The WordPress connection use when running the Export Posts task.

### Output File
_Required_
The file to save results from the Export Posts task. The results are returned as an array of the Post object as detailed in the example below.

### WooCommerce Export Settings
See [Common WordPress Settings](common-wordpress-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


A sample output file is shown below.


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfPost xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <Post>
        <id>31</id>
        <external_id>12345</external_id>
        <link>https://localhost/wordpress/a-post/</link>
        <date>2016-08-02T16:31:53</date>
        <date_gmt>2016-08-02T15:31:53</date_gmt>
        <modified>2016-08-31T15:59:40</modified>
        <modified_gmt>2016-08-31T14:59:40</modified_gmt>
        <slug>a-post</slug>
        <type>post</type>
        <title>
          <rendered>a post</rendered>
        </title>
        <author_id>1</author_id>
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
        <featured_media>0</featured_media>
        <comment_status>open</comment_status>
        <ping_status>open</ping_status>
        <format>standard</format>
        <sticky>false</sticky>
        <categories>
          <Category>
            <id>9</id>
            <count>1</count>
            <description />
            <link>https://localhost/wordpress/category/parent-category/child-category/</link>
            <name>Child Category</name>
            <slug>child-category</slug>
            <taxonomy>category</taxonomy>
            <parent>8</parent>
          </Category>
          <Category>
            <id>8</id>
            <count>1</count>
            <description />
            <link>https://localhost/wordpress/category/parent-category/</link>
            <name>Parent Category</name>
            <slug>parent-category</slug>
            <taxonomy>category</taxonomy>
            <parent>0</parent>
          </Category>
          <Category>
            <id>1</id>
            <count>2</count>
            <description />
            <link>https://localhost/wordpress/category/uncategorised/</link>
            <name>Uncategorised</name>
            <slug>uncategorised</slug>
            <taxonomy>category</taxonomy>
            <parent>0</parent>
          </Category>
        </categories>
        <tags>
          <Tag>
            <id>10</id>
            <count>1</count>
            <description />
            <link>https://localhost/wordpress/tag/news/</link>
            <name>news</name>
            <slug>news</slug>
            <taxonomy>post_tag</taxonomy>
          </Tag>
        </tags>
      </Post>
    </ArrayOfPost>
```