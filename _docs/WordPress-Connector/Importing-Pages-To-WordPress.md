---
slug: importing-pages-to-wordpress
redirect_from: "/article/917-uploading-pages-to-wordpress"
title: Importing Pages To WordPress
---


This task will insert new and update existing pages in WordPress, from an XML file. The logic surrounding whether to insert or update a page works as follows:


1. If an `id` is provided for the page, the existing page will be updated.
2. If an `external_id` is provided for the page, and a match is found  in Zynk's [truth table](storage), the existing page will be updated.
3. If a `slug` is provided for the page, and a match is found in WordPress, the existing page will be updated.
4. If none of the above conditions are fulfilled, a new page will be created.

## Settings

### Fail File
_Required_  
The XML file to save any pages to that failed to import to WordPress.	  

### Input File
_Required_  
The XML file containing the pages to upload to WordPress. See below for a sample input file.

### Success File
_Required_  
The XML file to save successfully imported pages to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same page being processed more than once by the task. This only works where an `external_id` is provided for the page

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
		<date>2015-09-08T12:42:17</date>
		<date_gmt>2015-09-08T11:42:17</date_gmt>
		<guid>
			<rendered>http://localhost:8080/wordpress/?page_id=2</rendered>
		</guid>
		<link>https://localhost/wordpress/sample-page/</link>
		<slug>sample-page</slug>
		<type>page</type>
		<parent>
			<id>0</id>
		</parent>
		<title>
			<rendered>Sample Page</rendered>
		</title>
		<content>
          <rendered>gt;&lt;p&gt;This is an example page. It&amp;#8217;s different from a blog post because it will stay in one place and will show up in your site navigation (in most themes). Most people start with an About page that introduces them to potential site visitors. It might say something like this:&lt;/p&gt;
    &lt;blockquote&gt;&lt;p&gt;Hi there! I&amp;#8217;m a bike messenger by day, aspiring actor by night, and this is my blog. I live in Los Angeles, have a great dog named Jack, and I like pi&amp;#241;a coladas. (And gettin&amp;#8217; caught in the rain.)&lt;/p&gt;&lt;/blockquote&gt;
    &lt;p&gt;&amp;#8230;or something like this:&lt;/p&gt;
    &lt;blockquote&gt;&lt;p&gt;The XYZ Doohickey Company was founded in 1971, and has been providing quality doohickeys to the public ever since. Located in Gotham City, XYZ employs over 2,000 people and does all kinds of awesome things for the Gotham community.&lt;/p&gt;&lt;/blockquote&gt;
    &lt;p&gt;As a new WordPress user, you should go to &lt;a href="http://localhost:8080/wordpress/wp-admin/"&gt;your dashboard&lt;/a&gt; to delete this page and create new pages for your content. Have fun!&lt;/p&gt;</rendered>
		</content>
		<author>
			<id>1</id>
			<slug>admin</slug>
		</author>
		<excerpt>
			<rendered>
				&lt;p&gt;This is an example page. It&amp;#8217;s different from a blog post because it will stay in one place and will show up in your site navigation (in most themes). Most people start with an About page that introduces them to potential site visitors. It might say something like this: Hi there! I&amp;#8217;m a bike messenger &amp;hellip; &lt;a href="https://localhost/wordpress/sample-page/" class="more-link"&gt;Continue reading &lt;span class="screen-reader-text"&gt;Sample Page&lt;/span&gt;
					&lt;/a&gt;
				&lt;/p&gt;
			</rendered>
		</excerpt>
		<featured_media>0</featured_media>
		<comment_status>open</comment_status>
		<ping_status>open</ping_status>
		<menu_order>0</menu_order>
		<template />
	</Page>
</ArrayOfPage>
```