---
slug: importing-posts-to-wordpress
redirect_from: "/article/918-uploading-posts-to-wordpress"
title: Importing Posts To WordPress
---


This task will insert new and update existing posts in WordPress, from an XML file. The logic surrounding whether to insert or update a post works as follows:


1. If an `id` is provided for the post, the existing post will be updated.
2. If an `external_id` is provided for the post, and a match is found  in Zynk's [truth table](storage), the existing post will be updated.
3. If a `slug` is provided for the post, and a match is found in WordPress, the existing post will be updated.
4. If none of the above conditions are fulfilled, a new post will be created.


## Upload Posts

## Settings

### Fail File
_Required_  
The XML file to save any posts to that failed to import to WordPress.	  

### Input File
_Required_  
The XML file containing the posts to upload to WordPress. See below for a sample input file.

### Success File
_Required_  
The XML file to save successfully imported posts to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same post being processed more than once by the task. This only works where an `external_id` is provided for the post

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


A sample input file is shown below.


```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPost xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Post>
    <id>31</id>
    <external_id>12345</external_id>
    <link>https://localhost/wordpress/a-post/</link>
    <slug>a-post</slug>
    <type>post</type>
    <title>
      <rendered>a post</rendered>
    </title>
    <content>
      <rendered>&lt;p&gt;Welcome to WordPress. This is your first post. Edit or delete it, then start writing!&lt;/p&gt;</rendered>
    </content>
    <author>
      <id>1</id>
      <slug>admin</slug>
    </author>
    <excerpt>
      <rendered>&lt;p&gt;Welcome to WordPress. This is your first post. Edit or delete it, then start writing!&lt;/p&gt;</rendered>
    </excerpt>
    <featured_media>0</featured_media>
    <comment_status>open</comment_status>
    <ping_status>open</ping_status>
    <format>standard</format>
    <sticky>false</sticky>
    <categories>
      <Category>
        <id>9</id>
        <slug>child-category</slug>
      </Category>
      <Category>
        <id>8</id>
        <slug>parent-category</slug>
      </Category>
      <Category>
        <id>1</id>
        <slug>uncategorised</slug>
      </Category>
    </categories>
    <tags>
      <Tag>
        <id>10</id>
        <slug>news</slug>
      </Tag>
    </tags>
  </Post>
</ArrayOfPost>
```
