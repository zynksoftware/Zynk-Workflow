---
slug: downloading-products-from-shopify
redirect_from: "/article/310-downloading-products-from-shopify"
title: Downloading Products from Shopify
---
This task will download a list of products from your Shopify store, and save them to an XML file.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Download All
_Required_  
Set this option to true to download all products, or set to false to only download new or modified products since the task was last ran.

### Output File
_Required_  
The XML file to save the list of products to.

### Status
_Required_  
Set this option to 'Any' to download products regardless of their published status, or set this option to only download products which are either published or unpublished. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<products type="array">
  <product>
    <body-html><p>So this is a product.</p>
<p>The text you see here is a Product Description. Every product has a price, a weight, a picture and a description.  To edit the description of this product or to create a new product you can go to the <a href="/admin/products">Products Tab</a> of the administration menu.</p>
<p>Once you have mastered the creation and editing of products you will want your products to show up on your Shopify site.  There is a two step process to do this.</p>
<p>First you need to add your products to a Collection.  A Collection is an easy way to group products together. If you go to the <a href="/admin/custom_collections">Collections Tab</a> of the administration menu you can begin creating collections and adding products to them.</p>
<p>Second you&#8217;ll need to create a link from your shop&#8217;s navigation menu to your Collections. You can do this by going to the <a href="/admin/links">Navigations Tab</a> of the administration menu and clicking on &#8220;Add a link&#8221;.</p>
<p>Good luck with your shop!</p></body-html>
    <created-at type="datetime">2012-08-15T10:56:05-04:00</created-at>
    <handle>networked-homogeneous-methodology</handle>
    <id type="integer">100040852</id>
    <product-type>Shirts</product-type>
    <published-at type="datetime" nil="true" />
    <template-suffix nil="true" />
    <title>Networked homogeneous methodology</title>
    <updated-at type="datetime">2012-09-06T11:47:54-04:00</updated-at>
    <vendor>Shopify</vendor>
    <tags>Demo, T-Shirt</tags>
    <variants type="array">
      <variant>
        <compare-at-price type="decimal" nil="true" />
        <created-at type="datetime">2012-08-15T10:56:05-04:00</created-at>
        <fulfillment-service>manual</fulfillment-service>
        <grams type="integer">0</grams>
        <id type="integer">232945606</id>
        <inventory-management nil="true" />
        <inventory-policy>deny</inventory-policy>
        <option1>Medium</option1>
        <option2 nil="true" />
        <option3 nil="true" />
        <position type="integer">1</position>
        <price type="decimal">19.00</price>
        <product-id type="integer">100040852</product-id>
        <requires-shipping type="boolean">true</requires-shipping>
        <sku></sku>
        <taxable type="boolean">true</taxable>
        <title>Medium</title>
        <updated-at type="datetime">2012-08-15T10:56:05-04:00</updated-at>
        <inventory-quantity type="integer">1</inventory-quantity>
      </variant>
    </variants>
    <images type="array" />
    <options type="array">
      <option>
        <id type="integer">119545988</id>
        <name>Title</name>
        <position type="integer">1</position>
        <product-id type="integer">100040852</product-id>
      </option>
    </options>
  </product>
</products>
```