---
slug: downloading-orders-from-bigcommerce
redirect_from: "/article/168-downloading-orders-from-bigcommerce"
title: Downloading Orders from BigCommerce
---
This task will download orders taken on your BigCommerce store to an XML file.

## Settings
### Connection
_Required_  
The BigCommerce connection to use.See the [Connecting to BigCommerce](connecting-to-bigcommerce) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all orders from your store, or set to false to download only new or modified orders since this task last ran. Defaults to false.

### Download Stage
_Required_  
The status of the orders to be downloaded. Can be set to 'Any' to download orders regardless of their status.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. orders.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
You can find an example of how to use this task in the [BigCommerce to Sage 50 Integration](bigcommerce-to-sage-50-integration) article.

Sample output file showing a the order 105:

```xml
<?xml version="1.0" encoding="utf-8"?>
<orders>
  <order>
    <id>105</id>
    <customer_id>1</customer_id>
    <date_created>Fri, 09 Aug 2013 13:18:20 +0000</date_created>
    <date_modified>Fri, 25 Oct 2013 09:11:04 +0000</date_modified>
    <date_shipped></date_shipped>
    <status_id>11</status_id>
    <status>Awaiting Fulfillment</status>
    <subtotal_ex_tax>499.0000</subtotal_ex_tax>
    <subtotal_inc_tax>598.8000</subtotal_inc_tax>
    <subtotal_tax>99.8000</subtotal_tax>
    <base_shipping_cost>0.0000</base_shipping_cost>
    <shipping_cost_ex_tax>0.0000</shipping_cost_ex_tax>
    <shipping_cost_inc_tax>0.0000</shipping_cost_inc_tax>
    <shipping_cost_tax>0.0000</shipping_cost_tax>
    <shipping_cost_tax_class_id>2</shipping_cost_tax_class_id>
    <base_handling_cost>0.0000</base_handling_cost>
    <handling_cost_ex_tax>0.0000</handling_cost_ex_tax>
    <handling_cost_inc_tax>0.0000</handling_cost_inc_tax>
    <handling_cost_tax>0.0000</handling_cost_tax>
    <handling_cost_tax_class_id>2</handling_cost_tax_class_id>
    <base_wrapping_cost>0.0000</base_wrapping_cost>
    <wrapping_cost_ex_tax>0.0000</wrapping_cost_ex_tax>
    <wrapping_cost_inc_tax>0.0000</wrapping_cost_inc_tax>
    <wrapping_cost_tax>0.0000</wrapping_cost_tax>
    <wrapping_cost_tax_class_id>3</wrapping_cost_tax_class_id>
    <total_ex_tax>489.0000</total_ex_tax>
    <total_inc_tax>586.8000</total_inc_tax>
    <total_tax>97.8000</total_tax>
    <items_total>1</items_total>
    <items_shipped>0</items_shipped>
    <payment_method>Cash on Delivery</payment_method>
    <payment_provider_id>NULL</payment_provider_id>
    <payment_status></payment_status>
    <refunded_amount>0.0000</refunded_amount>
    <order_is_digital>false</order_is_digital>
    <store_credit_amount>0.0000</store_credit_amount>
    <gift_certificate_amount>0.0000</gift_certificate_amount>
    <ip_address>XXX.XXX.XXX.XXX</ip_address>
    <geoip_country>United Kingdom</geoip_country>
    <geoip_country_iso2>GB</geoip_country_iso2>
    <currency_id>1</currency_id>
    <currency_code>GBP</currency_code>
    <currency_exchange_rate>1.0000000000</currency_exchange_rate>
    <default_currency_id>1</default_currency_id>
    <default_currency_code>GBP</default_currency_code>
    <staff_notes>This is a test staff note comment.</staff_notes>
    <customer_message>This is a test order comment.</customer_message>
    <discount_amount>10.0000</discount_amount>
    <coupon_discount>0.0000</coupon_discount>
    <shipping_address_count>1</shipping_address_count>
    <is_deleted>false</is_deleted>
    <ebay_order_id>0</ebay_order_id>
    <billing_address>
      <first_name>Joe</first_name>
      <last_name>Harrison</last_name>
      <company>Zynk Software Limited</company>
      <street_1>6-8 Charlotte Square</street_1>
      <street_2>i6</street_2>
      <city>Newcastle upon-Tyne</city>
      <state>Tyne and Wear</state>
      <zip>NE1 4XF</zip>
      <country>United Kingdom</country>
      <country_iso2>GB</country_iso2>
      <phone>0845 123 2920</phone>
      <email>joe.harrison@zynk.com</email>
    </billing_address>
    <order_source>manual</order_source>
    <external_source>NULL</external_source>
    <products>
      <product>
        <id>7</id>
        <order_id>105</order_id>
        <product_id>186</product_id>
        <order_address_id>6</order_address_id>
        <name>iPhone 4 16GB White</name>
        <sku>IPHONE4</sku>
        <type>physical</type>
        <base_price>499.0000</base_price>
        <price_ex_tax>499.0000</price_ex_tax>
        <price_inc_tax>598.8000</price_inc_tax>
        <price_tax>99.8000</price_tax>
        <base_total>499.0000</base_total>
        <total_ex_tax>499.0000</total_ex_tax>
        <total_inc_tax>598.8000</total_inc_tax>
        <total_tax>99.8000</total_tax>
        <weight>0.0000</weight>
        <quantity>1</quantity>
        <base_cost_price>0.0000</base_cost_price>
        <cost_price_inc_tax>0.0000</cost_price_inc_tax>
        <cost_price_ex_tax>0.0000</cost_price_ex_tax>
        <cost_price_tax>0.0000</cost_price_tax>
        <is_refunded>false</is_refunded>
        <refund_amount>0.0000</refund_amount>
        <return_id>0</return_id>
        <wrapping_name></wrapping_name>
        <base_wrapping_cost>0.0000</base_wrapping_cost>
        <wrapping_cost_ex_tax>0.0000</wrapping_cost_ex_tax>
        <wrapping_cost_inc_tax>0.0000</wrapping_cost_inc_tax>
        <wrapping_cost_tax>0.0000</wrapping_cost_tax>
        <wrapping_message></wrapping_message>
        <quantity_shipped>0</quantity_shipped>
        <event_name>NULL</event_name>
        <event_date></event_date>
        <fixed_shipping_cost>0.0000</fixed_shipping_cost>
        <ebay_item_id></ebay_item_id>
        <ebay_transaction_id></ebay_transaction_id>
        <option_set_id>NULL</option_set_id>
        <parent_order_product_id>NULL</parent_order_product_id>
        <is_bundled_product>false</is_bundled_product>
        <bin_picking_number></bin_picking_number>
        <applied_discounts>
          <discount>
            <id>manual-discount</id>
            <amount>10.00</amount>
          </discount>
        </applied_discounts>
        <product_options />
        <configurable_fields />
      </product>
    </products>
    <shipping_addresses>
      <address>
        <id>6</id>
        <order_id>105</order_id>
        <first_name>Joe</first_name>
        <last_name>Harrison</last_name>
        <company>Zynk Software Limited</company>
        <street_1>6-8 Charlotte Square</street_1>
        <street_2>i6</street_2>
        <city>Newcastle upon-Tyne</city>
        <zip>NE1 4XF</zip>
        <country>United Kingdom</country>
        <country_iso2>GB</country_iso2>
        <state>Tyne and Wear</state>
        <email></email>
        <phone>0845 123 2920</phone>
        <items_total>1</items_total>
        <items_shipped>0</items_shipped>
        <shipping_method>None</shipping_method>
        <base_cost>0.0000</base_cost>
        <cost_ex_tax>0.0000</cost_ex_tax>
        <cost_inc_tax>0.0000</cost_inc_tax>
        <cost_tax>0.0000</cost_tax>
        <cost_tax_class_id>2</cost_tax_class_id>
        <base_handling_cost>0.0000</base_handling_cost>
        <handling_cost_ex_tax>0.0000</handling_cost_ex_tax>
        <handling_cost_inc_tax>0.0000</handling_cost_inc_tax>
        <handling_cost_tax>0.0000</handling_cost_tax>
        <handling_cost_tax_class_id>2</handling_cost_tax_class_id>
        <shipping_zone_id>1</shipping_zone_id>
        <shipping_zone_name>Default Zone</shipping_zone_name>
      </address>
    </shipping_addresses>
    <coupons></coupons>
  </order>
</orders>
```

Sample XSLT file to use to transform the output file from this task to the Zynk XML Sale Orders format, ready for import into Sage. This is also available in the [Auto Mapper](auto-mapper).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">
  <xsl:output method="xml" indent="yes"/>

  <xsl:param name="WebSales">false</xsl:param> <!-- All sales to a single account { true, false } -->
  <xsl:param name="AccountReference">WEB</xsl:param> <!-- Web sales account reference -->
  <xsl:param name="BankAccount">1200</xsl:param> <!-- Bank account reference -->

  <xsl:template match="/">
    <Company>
      <SalesOrders>
        <xsl:for-each select="orders/order">
          <xsl:call-template name="SalesOrder" /> 
        </xsl:for-each>
      </SalesOrders>
    </Company>
  </xsl:template>

  <xsl:template name="SalesOrder">
    <SalesOrder>
      <Id><xsl:value-of select="id"/></Id>
      <CustomerId><xsl:value-of select="customer_id"/></CustomerId>
      <SalesOrderNumber><xsl:value-of select="id"/></SalesOrderNumber>
      <CustomerOrderNumber><xsl:value-of select="id"/></CustomerOrderNumber>
      <Notes1><xsl:value-of select="customer_message"/></Notes1>
      <Notes2><xsl:value-of select="staff_notes"/></Notes2>
      <Currency><xsl:value-of select="currency_code"/></Currency>

      <AccountReference>
        <xsl:if test="$WebSales = 'true' or customer_id = 0">
          <xsl:value-of select="$AccountReference"/>
        </xsl:if>
      </AccountReference>

      <xsl:choose>
        <xsl:when test="currency_code = 'GBP'">
          <CurrencyUsed>false</CurrencyUsed>
        </xsl:when>
        <xsl:otherwise>
          <CurrencyUsed>true</CurrencyUsed>
        </xsl:otherwise>
      </xsl:choose> 
      <SalesOrderDate>
        <xsl:call-template name="formatDate">
          <xsl:with-param name="dateTimeStr" select="date_created" />
        </xsl:call-template>
      </SalesOrderDate>

      <SalesOrderAddress>
        <Forename><xsl:value-of select="billing_address/first_name"/></Forename>
        <Surname><xsl:value-of select="billing_address/last_name"/></Surname>

        <xsl:if test="billing_address/company != ''">
          <Company><xsl:value-of select="billing_address/company"/></Company>
        </xsl:if>

        <Address1><xsl:value-of select="billing_address/street_1"/></Address1>
        <Address2><xsl:value-of select="billing_address/street_2"/></Address2>
        <Town><xsl:value-of select="billing_address/city"/></Town>
        <Postcode><xsl:value-of select="billing_address/zip"/></Postcode>
        <County><xsl:value-of select="billing_address/state"/></County>
        <Country><xsl:value-of select="billing_address/country"/></Country>
        <Telephone><xsl:value-of select="billing_address/phone"/></Telephone>
        <Email><xsl:value-of select="billing_address/email"/></Email>
      </SalesOrderAddress>

      <SalesOrderDeliveryAddress>
        <Forename><xsl:value-of select="shipping_addresses/address[1]/first_name"/></Forename>
        <Surname><xsl:value-of select="shipping_addresses/address[1]/last_name"/></Surname>

        <xsl:if test="shipping_addresses/address[1]/company != ''">
          <Company><xsl:value-of select="shipping_addresses/address[1]/company"/></Company>
        </xsl:if>

        <Address1><xsl:value-of select="shipping_addresses/address[1]/street_1"/></Address1>
        <Address2><xsl:value-of select="shipping_addresses/address[1]/street_2"/></Address2>
        <Town><xsl:value-of select="shipping_addresses/address[1]/city"/></Town>
        <Postcode><xsl:value-of select="shipping_addresses/address[1]/zip"/></Postcode>
        <County><xsl:value-of select="shipping_addresses/address[1]/state"/></County>
        <Country><xsl:value-of select="shipping_addresses/address[1]/country"/></Country>
        <Telephone><xsl:value-of select="shipping_addresses/address[1]/phone"/></Telephone>
        <Email><xsl:value-of select="shipping_addresses/address[1]/email"/></Email>
      </SalesOrderDeliveryAddress>

      <SalesOrderItems>
        <xsl:for-each select="products/product">
          <xsl:call-template name="OrderItem"/>
        </xsl:for-each>
      </SalesOrderItems>

      <Carriage>
        <Sku><xsl:value-of select="sku"/></Sku>
        <Name>Shipping</Name>
        <QtyOrdered>1</QtyOrdered>
        <UnitPrice><xsl:value-of select="shipping_cost_ex_tax"/></UnitPrice>
        <TotalNet><xsl:value-of select="shipping_cost_ex_tax"/></TotalNet>
        <TotalTax><xsl:value-of select="shipping_cost_tax"/></TotalTax>
        <TaxCode>
          <xsl:choose>
            <xsl:when test="shipping_cost_tax > 0">1</xsl:when>
            <xsl:otherwise>0</xsl:otherwise>
          </xsl:choose>
        </TaxCode>
      </Carriage>

      <TakenBy>BigCommerce</TakenBy>
      <PaymentAmount><xsl:value-of select="total_inc_tax"/></PaymentAmount>
      <BankAccount><xsl:value-of select="$BankAccount"/></BankAccount>
      <PaymentReference><xsl:value-of select="payment_method"/></PaymentReference>
    </SalesOrder>
  </xsl:template>

  <!--Order items -->
  <xsl:template name="OrderItem">
    <Item>
      <Id><xsl:value-of select="id"/></Id>
      <Sku><xsl:value-of select="sku"/></Sku>
      <Name><xsl:value-of select="name"/></Name>
      <QtyOrdered><xsl:value-of select="quantity"/></QtyOrdered>
      <UnitPrice><xsl:value-of select="price_ex_tax"/></UnitPrice>
      <UnitDiscountAmount><xsl:value-of select="sum(applied_discounts/discount/amount) div quantity"/></UnitDiscountAmount>
      <QtyDispatched><xsl:value-of select="quantity_shipped"/></QtyDispatched>
      <TaxCode>
        <xsl:choose>
          <xsl:when test="price_tax > 0">1</xsl:when>
          <xsl:otherwise>0</xsl:otherwise>
        </xsl:choose>
      </TaxCode>
    </Item>
  </xsl:template>

  <!-- Converts a date to the correct format -->
  <xsl:template name="formatDate">
    <xsl:param name="dateTimeStr" />
    <xsl:variable name="dateTime" select="substring-after(substring-before($dateTimeStr, ' +'), ', ')" />
    <xsl:variable name="date" select="substring($dateTime,0,12)"/>
    <xsl:variable name="time" select="substring($dateTime,13)"/>

    <xsl:variable name="day" select="substring-before($date, ' ')"/>
    <xsl:variable name="monthStr" select="substring-before(substring-after($date, ' '), ' ')"/>
    <xsl:variable name="year" select="substring-after(substring-after($date, ' '), ' ')"/>

    <xsl:choose>
      <xsl:when test="$monthStr = 'Jan'">
        <xsl:value-of select="concat($year, '-01-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Feb'">
        <xsl:value-of select="concat($year, '-02-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Mar'">
        <xsl:value-of select="concat($year, '-03-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Apr'">
        <xsl:value-of select="concat($year, '-04-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'May'">
        <xsl:value-of select="concat($year, '-05-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Jun'">
        <xsl:value-of select="concat($year, '-06-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Jul'">
        <xsl:value-of select="concat($year, '-07-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Aug'">
        <xsl:value-of select="concat($year, '-08-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Sep'">
        <xsl:value-of select="concat($year, '-09-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Oct'">
        <xsl:value-of select="concat($year, '-10-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Nov'">
        <xsl:value-of select="concat($year, '-11-', $day, 'T', $time)" />
      </xsl:when>
      <xsl:when test="$monthStr = 'Dec'">
        <xsl:value-of select="concat($year, '-12-', $day, 'T', $time)" />
      </xsl:when>
    </xsl:choose>
  </xsl:template>

</xsl:stylesheet>
```