---
slug: exporting-comments-from-wordpress
redirect_from: "/article/913-downloading-comments-from-wordpress"
title: Exporting Comments From WordPress
---


This task will download comments from WordPress in an XML format. The results can be filtered if required. See below for a sample output file.

### Connection 
_Required_
The WordPress connection use when running the Export Comments task.

### Output File
_Required_
The file to save results from the Export Comments task. The results are returned as an array of the Comment object as detailed in the example below.

### WooCommerce Export Settings
See [Common WordPress Settings](common-wordpress-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


A sample output file is shown below.



    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfComment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <Comment>
        <id>1</id>
        <external_id>12345</external_id>
        <author_name>Mr WordPress</author_name>
        <author_url>https://wordpress.org/</author_url>
        <content>
          <rendered><p>Hi, this is a comment.<br />
    To delete a comment, just log in and view the post&amp;#039;s comments. There you will have the option to edit or delete them.</p></rendered>
        </content>
        <date>2015-09-08T12:42:17</date>
        <date_gmt>2015-09-08T11:42:17</date_gmt>
        <karma xsi:nil="true" />
        <link>https://localhost/wordpress/hello-world/#comment-1</link>
        <post>
          <id>1</id>
          <link>https://localhost/wordpress/hello-world/</link>
          <date>2015-09-08T12:42:17</date>
          <date_gmt>2015-09-08T11:42:17</date_gmt>
          <modified>2015-09-08T12:42:17</modified>
          <modified_gmt>2015-09-08T11:42:17</modified_gmt>
          <slug>hello-world</slug>
          <type>post</type>
          <title>
            <rendered>Hello world!</rendered>
          </title>
          <content>
            <rendered><p>Welcome to WordPress. This is your first post. Edit or delete it, then start writing!</p></rendered>
          </content>
          <author>
            <id>1</id>
            <registered_date xsi:nil="true" />
          </author>
          <excerpt>
            <rendered><p>Welcome to WordPress. This is your first post. Edit or delete it, then start writing!</p></rendered>
          </excerpt>
          <featured_media>0</featured_media>
          <comment_status>open</comment_status>
          <ping_status>open</ping_status>
          <format>standard</format>
          <sticky>false</sticky>
          <categories>
            <Category>
              <id>1</id>
              <count xsi:nil="true" />
              <parent xsi:nil="true" />
            </Category>
          </categories>
          <tags />
        </post>
        <status>approved</status>
        <type>comment</type>
        <author_avatar_urls>
          <item>
            <key>24</key>
            <value>https://secure.gravatar.com/avatar/?s=24&amp;d=mm&amp;r=g</value>
          </item>
          <item>
            <key>48</key>
            <value>https://secure.gravatar.com/avatar/?s=48&amp;d=mm&amp;r=g</value>
          </item>
          <item>
            <key>96</key>
            <value>https://secure.gravatar.com/avatar/?s=96&amp;d=mm&amp;r=g</value>
          </item>
        </author_avatar_urls>
      </Comment>
    </ArrayOfComment>

