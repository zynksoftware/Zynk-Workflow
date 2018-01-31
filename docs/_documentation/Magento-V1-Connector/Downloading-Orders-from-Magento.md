---
slug: downloading-orders-from-magento
redirect_from: "/article/262-downloading-orders-from-magento"
title: Downloading Orders from Magento
---
This task will download orders from Magento in XML format. You can choose to only download orders created/updated since the last time the task was run, or select certain orders based on a filter (such as those with the status 'Processing'). See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all records (which match the filter if one is specified - including start date), or false to download only new/modified orders.

### Download From
_Optional_  
The date to download new/modified orders from. Updates automatically each time the task runs.

### Start Date
_Optional_  
No orders created before this date will be downloaded, even if they are modified.

### Output File
_Required_  
The name of the file to export the orders to.

### Filter Property
_Optional_  
The property the filter is to be based upon. The property name should match the API field name, as seen in the output file.

### Filter Type
_Optional_  
The following types of filter are available:

* __eq__ - Returns records where the property matches the specified value
* __gt__ - Returns records where the property is greater than the specified value
* __lt__ - Returns records where the property is less than the specified value.
* __like__ - Returns records where the property contains the specified value.
* __isnull__ - Returns records where the property is null.
* __notnull__ - Returns records where the property is not null.

### Filter Value
_Optional_  
The value the filter is to be based upon. When using the eq filter type, you can specify multiple values by separating them with commas, or using the 'Use a list' option after clicking the ellipsis (...) button.

### Download Stage
_Optional_  
Set the status of the orders to be downloaded (e.g. pending, processing, complete). Multiple statuses can be entered by separating them with commas, or using the 'Use a list' option after clicking the ellipsis (...) button.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0"?>
<ArrayOfOrderInfo>
  <OrderInfo>
    <shipping_address>
      <city>Newcastle</city>
      <address_type>shipping</address_type>
      <firstname>Andrew</firstname>
      <lastname>Snape</lastname>
      <company>Internetware</company>
      <street>Newcastle Business Centre 6 Charlotte Square</street>
      <region>Tyne and Wear</region>
      <postcode>NE1 4XF</postcode>
      <country_id>GB</country_id>
      <telephone>XXXXX XXX XXX</telephone>
      <fax />
      <address_id>6</address_id>
      <parent_id>3</parent_id>
    </shipping_address>
    <billing_address>
      <city>Newcastle</city>
      <address_type>billing</address_type>
      <firstname>Andrew</firstname>
      <lastname>Snape</lastname>
      <company>Internetware</company>
      <street>Newcastle Business Centre 6 Charlotte Square</street>
      <region>Tyne and Wear</region>
      <postcode>NE1 4XF</postcode>
      <country_id>GB</country_id>
      <telephone>XXXXX XXX XXX</telephone>
      <fax />
      <address_id>5</address_id>
      <parent_id>3</parent_id>
    </billing_address>
    <items>
      <OrderProduct>
        <created_at>2011-08-02 13:46:26</created_at>
        <updated_at>2011-08-17 11:56:27</updated_at>
        <product_id>162</product_id>
        <gift_message_available>2</gift_message_available>
        <sku>micronmouse5000</sku>
        <name>Microsoft Wireless Optical Mouse 5000</name>
        <weight>1.0000</weight>
        <price>59.9900</price>
        <order_id>3</order_id>
        <quote_item_id>4</quote_item_id>
        <product_type>simple</product_type>
        <product_options>a:5:{s:15:"info_buyRequest";a:2:{s:3:"qty";i:1;s:7:"options";a:0:{}s:17:"giftcard_lifetime";N;s:22:"giftcard_is_redeemable";i:0;s:23:"giftcard_email_template";N;s:13:"giftcard_type";N;}</product_options>
        <is_virtual>0</is_virtual>
        <applied_rule_ids />
        <free_shipping>0</free_shipping>
        <is_qty_decimal>0</is_qty_decimal>
        <no_discount>0</no_discount>
        <qty_canceled>0.0000</qty_canceled>
        <qty_invoiced>0.0000</qty_invoiced>
        <qty_ordered>1.0000</qty_ordered>
        <qty_refunded>0.0000</qty_refunded>
        <qty_shipped>0.0000</qty_shipped>
        <base_price>59.9900</base_price>
        <original_price>59.9900</original_price>
        <base_original_price>59.9900</base_original_price>
        <tax_percent>20.0000</tax_percent>
        <tax_amount>12.0000</tax_amount>
        <base_tax_amount>12.0000</base_tax_amount>
        <tax_invoiced>0.0000</tax_invoiced>
        <base_tax_invoiced>0.0000</base_tax_invoiced>
        <discount_percent>0.0000</discount_percent>
        <discount_amount>0.0000</discount_amount>
        <base_discount_amount>0.0000</base_discount_amount>
        <discount_invoiced>0.0000</discount_invoiced>
        <base_discount_invoiced>0.0000</base_discount_invoiced>
        <amount_refunded>0.0000</amount_refunded>
        <base_amount_refunded>0.0000</base_amount_refunded>
        <row_total>59.9900</row_total>
        <base_row_total>59.9900</base_row_total>
        <row_invoiced>0.0000</row_invoiced>
        <base_row_invoiced>0.0000</base_row_invoiced>
        <row_weight>1.0000</row_weight>
        <weee_tax_applied>a:0:{}</weee_tax_applied>
        <weee_tax_applied_amount>0.0000</weee_tax_applied_amount>
        <weee_tax_applied_row_amount>0.0000</weee_tax_applied_row_amount>
        <base_weee_tax_applied_amount>0.0000</base_weee_tax_applied_amount>
        <base_weee_tax_applied_row_amount>0.0000</base_weee_tax_applied_row_amount>
        <weee_tax_disposition>0.0000</weee_tax_disposition>
        <weee_tax_row_disposition>0.0000</weee_tax_row_disposition>
        <base_weee_tax_disposition>0.0000</base_weee_tax_disposition>
        <base_weee_tax_row_disposition>0.0000</base_weee_tax_row_disposition>
        <has_children>false</has_children>
      </OrderProduct>
    </items>
    <payment>
      <parent_id>3</parent_id>
      <amount_ordered>77.9900</amount_ordered>
      <base_amount_ordered>77.9900</base_amount_ordered>
      <shipping_amount>5.0000</shipping_amount>
      <base_shipping_amount>5.0000</base_shipping_amount>
      <cc_exp_month>0</cc_exp_month>
      <cc_exp_year>0</cc_exp_year>
      <method>checkmo</method>
      <po_number />
      <cc_type />
      <cc_number_enc />
      <cc_last4 />
      <cc_owner />
      <cc_ss_start_month>0</cc_ss_start_month>
      <cc_ss_start_year>0</cc_ss_start_year>
      <payment_id>3</payment_id>
    </payment>
    <status_history>
      <OrderStatus>
        <parent_id>3</parent_id>
        <store_id>1</store_id>
        <created_at>2011-08-02 13:46:26</created_at>
        <comment />
        <is_customer_notified>0</is_customer_notified>
        <status>pending</status>
      </OrderStatus>
    </status_history>
    <increment_id>100000003</increment_id>
    <store_id>1</store_id>
    <created_at>2011-08-02 13:46:26</created_at>
    <updated_at>2011-08-17 11:56:27</updated_at>
    <customer_id>2</customer_id>
    <tax_amount>13.0000</tax_amount>
    <shipping_amount>5.0000</shipping_amount>
    <discount_amount>0.0000</discount_amount>
    <subtotal>59.9900</subtotal>
    <grand_total>77.9900</grand_total>
    <total_qty_ordered>1.0000</total_qty_ordered>
    <base_tax_amount>13.0000</base_tax_amount>
    <base_shipping_amount>5.0000</base_shipping_amount>
    <base_discount_amount>0.0000</base_discount_amount>
    <base_subtotal>59.9900</base_subtotal>
    <base_grand_total>77.9900</base_grand_total>
    <shipping_tax_amount>1.0000</shipping_tax_amount>
    <base_shipping_tax_amount>1.0000</base_shipping_tax_amount>
    <weight>1.0000</weight>
    <store_to_base_rate>1.0000</store_to_base_rate>
    <store_to_order_rate>1.0000</store_to_order_rate>
    <base_to_global_rate>1.0000</base_to_global_rate>
    <base_to_order_rate>1.0000</base_to_order_rate>
    <shipping_description>Flat Rate - Fixed</shipping_description>
    <shipping_method>flatrate_flatrate</shipping_method>
    <status>pending</status>
    <base_currency_code>GBP</base_currency_code>
    <store_currency_code>GBP</store_currency_code>
    <order_currency_code>GBP</order_currency_code>
    <applied_rule_ids />
    <customer_email>support@zynk.com</customer_email>
    <state>new</state>
    <store_name>Main Website     Main Store     English</store_name>
    <global_currency_code>GBP</global_currency_code>
    <quote_id>7</quote_id>
    <shipping_address_id>6</shipping_address_id>
    <billing_address_id>5</billing_address_id>
    <is_virtual>0</is_virtual>
    <customer_group_id>1</customer_group_id>
    <customer_note_notify>0</customer_note_notify>
    <customer_is_guest>0</customer_is_guest>
    <order_id>3</order_id>
  </OrderInfo>
</ArrayOfOrderInfo>
```

Sample XSLT file to use to transform the output file from this task to the Zynk XML Sales Orders format, ready for import into Sage. This is also available in the [Auto Mapper](auto-mapper).
```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet 
  version="1.0"
  xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="xml" indent="yes"/>

  <xsl:param name="AccountReference" />
  <xsl:param name="BankAccount"/>
  <xsl:param name="TaxCode"/>

  <xsl:variable name="br"><xsl:text>&#10;</xsl:text></xsl:variable>
  <xsl:variable name="comma"><xsl:text>, </xsl:text></xsl:variable>

  <xsl:template match="ArrayOfOrderInfo">
    <Company>
      <SalesOrders>
        <xsl:for-each select="OrderInfo">
          <xsl:call-template name="SalesOrder" />
        </xsl:for-each>
      </SalesOrders>
    </Company>
  </xsl:template>

  <xsl:template name="SalesOrder">
    <SalesOrder>
      <Id><xsl:value-of select="order_id"/></Id>
      <CustomerId><xsl:value-of select="customer_id"/></CustomerId>
      <AccountReference><xsl:value-of select="$AccountReference"/></AccountReference>
      <SalesOrderNumber><xsl:value-of select="increment_id"/></SalesOrderNumber>
      <CustomerOrderNumber><xsl:value-of select="increment_id"/></CustomerOrderNumber>
      <SalesOrderDate><xsl:value-of select="substring-before(created_at, ' ')"/>T<xsl:value-of select="substring-after(created_at, ' ')"/></SalesOrderDate>

      <SalesOrderAddress>
        <!--<Title><xsl:value-of select="billing_address/firstname"/></Title>-->
        <Forename><xsl:value-of select="billing_address/firstname"/></Forename>
        <Surname><xsl:value-of select="billing_address/lastname"/></Surname>
        <Company><xsl:value-of select="billing_address/company"/></Company>

        <xsl:choose>
          <xsl:when test="contains(billing_address/street, $br)">
            <Address1>
              <xsl:value-of select="substring-before(billing_address/street, $br)"/>
            </Address1>
            <Address2>
              <xsl:call-template name="string-replace-all">
                <xsl:with-param name="text" select="substring-after(billing_address/street, $br)"/>
                <xsl:with-param name="replace" select="$br"/>
                <xsl:with-param name="by" select="$comma"/>
              </xsl:call-template>
            </Address2>
          </xsl:when>
          <xsl:otherwise>
            <Address1>
              <xsl:value-of select="billing_address/street"/>
            </Address1>
          </xsl:otherwise>
        </xsl:choose>

        <Town><xsl:value-of select="billing_address/city"/></Town>
        <Postcode><xsl:value-of select="billing_address/postcode"/></Postcode>
        <County><xsl:value-of select="billing_address/region"/></County>
        <Country><xsl:value-of select="billing_address/country_id"/></Country>
        <Telephone><xsl:value-of select="billing_address/telephone"/></Telephone>
        <Fax><xsl:value-of select="billing_address/fax"/></Fax>
        <Email><xsl:value-of select="customer_email"/></Email>
      </SalesOrderAddress>

      <SalesOrderDeliveryAddress>
        <!--<Title><xsl:value-of select="shipping_address/firstname"/></Title>-->
        <Forename><xsl:value-of select="shipping_address/firstname"/></Forename>
        <Surname><xsl:value-of select="shipping_address/lastname"/></Surname>
        <Company><xsl:value-of select="shipping_address/company"/></Company>

        <xsl:choose>
          <xsl:when test="contains(shipping_address/street, $br)">
            <Address1>
              <xsl:value-of select="substring-before(shipping_address/street, $br)"/>
            </Address1>
            <Address2>
              <xsl:call-template name="string-replace-all">
                <xsl:with-param name="text" select="substring-after(shipping_address/street, $br)"/>
                <xsl:with-param name="replace" select="$br"/>
                <xsl:with-param name="by" select="$comma"/>
              </xsl:call-template>
            </Address2>
          </xsl:when>
          <xsl:otherwise>
            <Address1>
              <xsl:value-of select="shipping_address/street"/>
            </Address1>
          </xsl:otherwise>
        </xsl:choose>

        <Town><xsl:value-of select="shipping_address/city"/></Town>
        <Postcode><xsl:value-of select="shipping_address/postcode"/></Postcode>
        <County><xsl:value-of select="shipping_address/region"/></County>
        <Country><xsl:value-of select="shipping_address/country_id"/></Country>
        <Telephone><xsl:value-of select="shipping_address/telephone"/></Telephone>
        <Fax><xsl:value-of select="shipping_address/fax"/></Fax>
        <Email><xsl:value-of select="customer_email"/></Email>
      </SalesOrderDeliveryAddress>

      <SalesOrderItems>
        <xsl:for-each select="items/OrderProduct">
          <xsl:call-template name="Item" />
        </xsl:for-each>
      </SalesOrderItems>

      <Carriage>
        <Sku><xsl:value-of select="shipping_method" /></Sku>
        <Name><xsl:value-of select="name" /></Name>
        <QtyOrdered><xsl:value-of select="1" /></QtyOrdered>
        <UnitPrice><xsl:value-of select="shipping_amount" /></UnitPrice>
        <TaxCode><xsl:value-of select="$TaxCode"/></TaxCode>
      </Carriage>

      <TakenBy>Magento</TakenBy>
      <PaymentRef><xsl:value-of select="payment/method"/></PaymentRef>
      <PaymentAmount><xsl:value-of select="payment/amount_ordered"/></PaymentAmount>
      <BankAccount><xsl:value-of select="$BankAccount"/></BankAccount>

    </SalesOrder>
  </xsl:template>

  <xsl:template name="Item">
    <Item>
      <Sku><xsl:value-of select="sku" /></Sku>
      <Name><xsl:value-of select="name" /></Name>
      <QtyOrdered><xsl:value-of select="qty_ordered" /></QtyOrdered>
      <UnitPrice><xsl:value-of select="price" /></UnitPrice>
      <TaxCode><xsl:value-of select="$TaxCode"/></TaxCode>
    </Item>
  </xsl:template>

  <xsl:template name="string-replace-all">
    <xsl:param name="text"/>
    <xsl:param name="replace"/>
    <xsl:param name="by"/>

    <xsl:choose>
      <xsl:when test="contains($text,$replace)">
        <xsl:value-of select="substring-before($text,$replace)"/>
        <xsl:value-of select="$by"/>
        <xsl:call-template name="string-replace-all">
          <xsl:with-param name="text" select="substring-after($text,$replace)"/>
          <xsl:with-param name="replace" select="$replace"/>
          <xsl:with-param name="by" select="$by"/>
        </xsl:call-template>
      </xsl:when>
      <xsl:otherwise>
        <xsl:value-of select="$text"/>
      </xsl:otherwise>
    </xsl:choose>
  </xsl:template>

</xsl:stylesheet>
```
