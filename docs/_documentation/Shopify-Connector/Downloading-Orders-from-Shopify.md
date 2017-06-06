---
slug: downloading-orders-from-shopify
redirect_from: "/article/309-downloading-orders-from-shopify"
title: Downloading Orders from Shopify
---
This task will download a list of orders from your Shopify store, and save them to an XML file. 

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Download All
_Required_  
Set this option to true to download all orders, or set to false to only download new or modified orders since the task was last ran.

### Output File
_Required_  
The XML file to save the list of orders to.

### Status
_Required_  
Set this option to 'Any' to download orders regardless of their status, or set this option to only download orders which have a particular status. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<orders type="array">
  <order>
    <buyer-accepts-marketing type="boolean">true</buyer-accepts-marketing>
    <cancel-reason nil="true" />
    <cancelled-at type="datetime" nil="true" />
    <cart-token>5c3cb3980ca0f415fefdeb3b5e929796</cart-token>
    <checkout-token nil="true" />
    <closed-at type="datetime" nil="true" />
    <confirmed type="boolean">true</confirmed>
    <created-at type="datetime">2012-08-16T07:49:39-04:00</created-at>
    <currency>GBP</currency>
    <email>support@zynk.com</email>
    <financial-status>authorized</financial-status>
    <fulfillment-status nil="true" />
    <gateway>bogus</gateway>
    <id type="integer">137673524</id>
    <landing-site>/</landing-site>
    <location-id type="integer" nil="true" />
    <name>#1004</name>
    <note></note>
    <number type="integer">4</number>
    <reference nil="true" />
    <referring-site></referring-site>
    <source nil="true" />
    <subtotal-price type="decimal">57.00</subtotal-price>
    <taxes-included type="boolean">false</taxes-included>
    <test type="boolean">true</test>
    <token>e12fcb57933fad968ae5be91954aaf01</token>
    <total-discounts type="decimal">0.00</total-discounts>
    <total-line-items-price type="decimal">57.00</total-line-items-price>
    <total-price type="decimal">77.00</total-price>
    <total-price-usd type="decimal">120.73</total-price-usd>
    <total-tax type="decimal">0.00</total-tax>
    <total-weight type="integer">0</total-weight>
    <updated-at type="datetime">2012-08-16T07:50:41-04:00</updated-at>
    <user-id type="integer" nil="true" />
    <browser-ip>000.000.000.000</browser-ip>
    <landing-site-ref nil="true" />
    <order-number type="integer">1004</order-number>
    <discount-codes type="array" />
    <note-attributes type="array"></note-attributes>
    <processing-method>direct</processing-method>
    <checkout-id nil="true" />
    <line-items type="array">
      <line-item>
        <fulfillment-service>manual</fulfillment-service>
        <fulfillment-status nil="true" />
        <grams type="integer">0</grams>
        <id type="integer">224202370</id>
        <price type="decimal">19.00</price>
        <product-id type="integer">100040856</product-id>
        <quantity type="integer">1</quantity>
        <requires-shipping type="boolean">true</requires-shipping>
        <sku></sku>
        <title>Proactive maximized monitoring</title>
        <variant-id type="integer">232945610</variant-id>
        <variant-title nil="true" />
        <vendor>Shopify</vendor>
        <name>Proactive maximized monitoring</name>
        <variant-inventory-management nil="true" />
        <properties type="array"></properties>
        <product-exists type="boolean">true</product-exists>
      </line-item>
      <line-item>
        <fulfillment-service>manual</fulfillment-service>
        <fulfillment-status nil="true" />
        <grams type="integer">0</grams>
        <id type="integer">224202372</id>
        <price type="decimal">19.00</price>
        <product-id type="integer">100040850</product-id>
        <quantity type="integer">2</quantity>
        <requires-shipping type="boolean">true</requires-shipping>
        <sku></sku>
        <title>Integrated hybrid internet solution</title>
        <variant-id type="integer">232945604</variant-id>
        <variant-title nil="true" />
        <vendor>Shopify</vendor>
        <name>Integrated hybrid internet solution</name>
        <variant-inventory-management nil="true" />
        <properties type="array"></properties>
        <product-exists type="boolean">true</product-exists>
      </line-item>
    </line-items>
    <shipping-lines type="array">
      <shipping-line>
        <code>International Shipping</code>
        <price type="decimal">20.00</price>
        <source>shopify</source>
        <title>International Shipping</title>
      </shipping-line>
    </shipping-lines>
    <tax-lines type="array" />
    <payment-details>
      <avs-result-code nil="true" />
      <credit-card-bin>1</credit-card-bin>
      <cvv-result-code nil="true" />
      <credit-card-number>XXXX-XXXX-XXXX-1</credit-card-number>
      <credit-card-company>Bogus</credit-card-company>
    </payment-details>
    <billing-address type="Address">
      <address1>Nelson House</address1>
      <address2>Fleming Business Centre</address2>
      <city>Newcastle</city>
      <company>Zynk Software</company>
      <country>United Kingdom</country>
      <first-name>John</first-name>
      <last-name>Smith</last-name>
      <latitude type="decimal">54.971188</latitude>
      <longitude type="decimal">-1.619922</longitude>
      <phone>0123456789</phone>
      <province>Tyne & Wear</province>
      <zip>NE2 3AE</zip>
      <name>John Smith</name>
      <country-code>GB</country-code>
      <province-code nil="true" />
    </billing-address>
    <shipping-address type="Address">
      <address1>Nelson House</address1>
      <address2>Fleming Business Centre</address2>
      <city>Newcastle</city>
      <company>Zynk Software</company>
      <country>United Kingdom</country>
      <first-name>John</first-name>
      <last-name>Smith</last-name>
      <latitude type="decimal">54.971188</latitude>
      <longitude type="decimal">-1.619922</longitude>
      <phone>0123456789</phone>
      <province>Tyne & Wear</province>
      <zip>NE2 3AE</zip>
      <name>John Smith</name>
      <country-code>GB</country-code>
      <province-code nil="true" />
    </shipping-address>
    <fulfillments type="array" />
    <client-details>
      <accept-language>en-us,en;q=0.5</accept-language>
      <browser-ip>000.000.000.000</browser-ip>
      <session-hash>d62d43425198941e2689157244cf400e1277d1b79ca91d257e339d67dfdb046f</session-hash>
      <user-agent>Mozilla/5.0 (Windows NT 6.1; WOW64; rv:14.0) Gecko/20100101 Firefox/14.0.1</user-agent>
    </client-details>
    <customer>
      <accepts-marketing type="boolean">true</accepts-marketing>
      <created-at type="datetime">2012-08-16T07:49:39-04:00</created-at>
      <email>support@zynk.com</email>
      <first-name>John</first-name>
      <id type="integer">96430088</id>
      <last-name>Smith</last-name>
      <last-order-id type="integer" nil="true" />
      <multipass-identifier nil="true" />
      <note>Update</note>
      <orders-count type="integer">0</orders-count>
      <state>disabled</state>
      <total-spent type="decimal">0.00</total-spent>
      <updated-at type="datetime">2012-11-30T08:24:43-05:00</updated-at>
      <verified-email type="boolean">true</verified-email>
      <tags></tags>
      <last-order-name nil="true" />
      <default-address>
        <address1>Nelson House</address1>
        <address2>Fleming Business Centre</address2>
        <city>Newcastle</city>
        <company>Zynk Software</company>
        <country>United Kingdom</country>
        <first-name>John</first-name>
        <id type="integer">133155492</id>
        <last-name>Smith</last-name>
        <phone>0123456789</phone>
        <province>Tyne & Wear</province>
        <zip>NE2 3AE</zip>
        <name>John Smith</name>
        <province-code nil="true" />
        <country-code>GB</country-code>
        <default type="boolean">true</default>
      </default-address>
    </customer>
  </order>
</orders>
```