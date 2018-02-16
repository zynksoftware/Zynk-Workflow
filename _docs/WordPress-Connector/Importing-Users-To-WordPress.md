---
slug: importing-users-to-wordpress
redirect_from: "/article/919-uploading-users-to-wordpress"
title: Importing Users To WordPress
---


This task will insert new and update existing users in WordPress, from an XML file. The logic surrounding whether to insert or update a user works as follows:


1. If an `id` is provided for the user, the existing user will be updated.
2. If an `external_id` is provided for the user, and a match is found  in Zynk's [truth table](storage), the existing user will be updated.
3. If a `slug` is provided for the user, and a match is found in WordPress, the existing user will be updated.
4. If none of the above conditions are fulfilled, a new user will be created.


## Upload Users

### Fail File
_Required_  
The XML file to save any posts to that failed to import to WordPress.	  

### Input File
_Required_  
The XML file containing the users to upload to WordPress. See below for a sample input file.

### Success File
_Required_  
The XML file to save successfully imported posts to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same user being processed more than once by the task. This only works where an `external_id` is provided for the user

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


A sample input file is shown below.



    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfUser xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <User>
        <id>2</id>
        <external_id>SMI001</external_id>
        <name>John</name>
        <url />
        <description />
        <link>https://localhost/wordpress/author/johnsmith/</link>
        <slug>johnsmith</slug>
        <registered_date xsi:nil="true" />
        <avatar_urls>
          <item>
            <key>24</key>
            <value>https://secure.gravatar.com/avatar/9b374134fd3322d5d7370b26d95b4b6d?s=24&amp;d=mm&amp;r=g</value>
          </item>
          <item>
            <key>48</key>
            <value>https://secure.gravatar.com/avatar/9b374134fd3322d5d7370b26d95b4b6d?s=48&amp;d=mm&amp;r=g</value>
          </item>
          <item>
            <key>96</key>
            <value>https://secure.gravatar.com/avatar/9b374134fd3322d5d7370b26d95b4b6d?s=96&amp;d=mm&amp;r=g</value>
          </item>
        </avatar_urls>
        <roles>
            <string>customer</string>
        </roles>
        <capabilities>
          <item>
            <key>read</key>
            <value>true</value>
          </item>
          <item>
            <key>edit_posts</key>
            <value>false</value>
          </item>
          <item>
            <key>delete_posts</key>
            <value>false</value>
          </item>
          <item>
            <key>customer</key>
            <value>true</value>
          </item>
        </capabilities>
        <extra_capabilities>
          <item>
            <key>customer</key>
            <value>true</value>
          </item>
        </extra_capabilities>
      </User>
    </ArrayOfUser>

