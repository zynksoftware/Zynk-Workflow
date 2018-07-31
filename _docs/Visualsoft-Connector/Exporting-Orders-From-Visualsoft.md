---
slug: exporting-orders-from-visualsoft
title: Exporting Orders from Visualsoft
---
This task will export orders from Visualsoft in an XML format. See below for a sample output file.

## Settings
### Connection
_Required_  
The Visualsoft connection to use. See the [Connecting to Visualsoft](connecting-to-visualsoft) article if you require more information on how to create/manage connections.

### Channel
_Required_ 
Select a specific channel to export orders from, or select 'All' to export from all channels. Please note that this setting only takes effect when the 'Export Modified, New or All Records' setting is set to 'NotNotified'.

### Export Settings > Export From
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'New' or 'Modified', only new or modified orders after this date will be exported. This date will update automatically each time the task runs.

### Export Settings > Export Modified, New or All Records
_Required_  
Choose which orders should be exported. The available options are:

* __New__ - Only orders created after the date shown in the 'Export From' setting will be exported.
* __Modified__ - Only orders updated after the date shown in the 'Export From' setting will be exported.
* __NotNotified__ - All orders which have not been notified (i.e. flagged as downloaded in Visualsoft) will be exported. Use this option in conjunction with the [Notify Orders](notifying-orders-in-visualsoft) task to control which orders are exported.

### Order IDs
_Optional_  
Specify specific order IDs to export from Visualsoft. Multiple IDs can be specified using a comma separated list. Use of this setting will override the 'Export Modified, New or All Records' and 'Channel' settings.

### Output File
_Required_  
The name of the file to export the orders to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<WEB_ORDERS xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <WEB_ORDER>
    <ORDER>
      <ORDER_ID>2561</ORDER_ID>
      <WEBSITE_ID>1</WEBSITE_ID>
      <ORDER_REFERENCE>WEB2561</ORDER_REFERENCE>
      <ORDER_STATUS_ID>2</ORDER_STATUS_ID>
      <ORDER_STATUS>Processing Order</ORDER_STATUS>
      <ORDER_FRAUD_STATE_ID>1</ORDER_FRAUD_STATE_ID>
      <ORDER_DATE>2018-07-08 10:01:04</ORDER_DATE>
      <UPDATED_DATE>2018-07-09 10:32:35</UPDATED_DATE>
      <DISPATCH_DATE />
      <ESTIMATED_DELIVERY_DATE />
      <DOWNLOADED>Y</DOWNLOADED>
      <DOWNLOADED_DATE>2018-07-08 10:03:11</DOWNLOADED_DATE>
      <PRODUCT_TOTAL_INC>10.488</PRODUCT_TOTAL_INC>
      <PRODUCT_TOTAL_EX>8.740</PRODUCT_TOTAL_EX>
      <PRODUCT_TOTAL_VAT>1.748</PRODUCT_TOTAL_VAT>
      <SHIPPING_TOTAL_INC>7.5</SHIPPING_TOTAL_INC>
      <SHIPPING_TOTAL_EX>6.250</SHIPPING_TOTAL_EX>
      <SHIPPING_TOTAL_VAT>1.250</SHIPPING_TOTAL_VAT>
      <DISCOUNT_TOTAL_INC>1.5</DISCOUNT_TOTAL_INC>
      <DISCOUNT_TOTAL_EX>1.250</DISCOUNT_TOTAL_EX>
      <DISCOUNT_TOTAL_VAT>0.250</DISCOUNT_TOTAL_VAT>
      <GRAND_TOTAL_INC>16.488</GRAND_TOTAL_INC>
      <GRAND_TOTAL_EX>13.74</GRAND_TOTAL_EX>
      <GRAND_TOTAL_VAT>2.748</GRAND_TOTAL_VAT>
      <ORDER_CURRENCY>GBP</ORDER_CURRENCY>
      <ORDER_CUSTOMER_COMMENTS>Leave by the door</ORDER_CUSTOMER_COMMENTS>
      <ORDER_NOTES />
      <ORDER_TYPE>WEB</ORDER_TYPE>
      <DELIVERY_METHOD>UK Standard Delivery</DELIVERY_METHOD>
      <GIFTWRAP_TOTAL_INC>0</GIFTWRAP_TOTAL_INC>
      <GIFTWRAP_TOTAL_NET>0</GIFTWRAP_TOTAL_NET>
      <GIFTWRAP_TOTAL_VAT>0</GIFTWRAP_TOTAL_VAT>
      <NUMBER_PRODUCTS>1</NUMBER_PRODUCTS>
      <MULTICHANNEL_SOURCE>
        <MULTICHANNEL_SOURCE_ID>5</MULTICHANNEL_SOURCE_ID>
        <MULTICHANNEL_SOURCE_NAME>Mobile</MULTICHANNEL_SOURCE_NAME>
      </MULTICHANNEL_SOURCE>
      <COURIER_STOCK_SYSTEM_REFERENCE_CODE />
      <PO_NUMBER>98765</PO_NUMBER>
      <CUSTOMER_DELIVERY_NOTES />
    </ORDER>
    <CUSTOMER>
      <CUSTOMER_ID>5642</CUSTOMER_ID>
      <BILLING_COMPANY_NAME>Zynk Software</BILLING_COMPANY_NAME>
      <BILLING_TITLE>Mr</BILLING_TITLE>
      <BILLING_FIRSTNAME>John</BILLING_FIRSTNAME>
      <BILLING_LASTNAME>Smith</BILLING_LASTNAME>
      <BILLING_ADDRESS1>Office 4</BILLING_ADDRESS1>
      <BILLING_ADDRESS2>6-8 Charlotte Square</BILLING_ADDRESS2>
      <BILLING_TOWN>Newcastle-upon-Tyne</BILLING_TOWN>
      <BILLING_COUNTY>Tyne &amp; Wear</BILLING_COUNTY>
      <BILLING_COUNTRY_ID>1</BILLING_COUNTRY_ID>
      <BILLING_COUNTRY>UK - Mainland</BILLING_COUNTRY>
      <BILLING_COUNTRY_CODE>GB</BILLING_COUNTRY_CODE>
      <BILLING_POSTCODE>Ne1 4XF</BILLING_POSTCODE>
      <BILLING_TELEPHONE>0191 303 7279</BILLING_TELEPHONE>
      <BILLING_EMAIL>support@zynk.com</BILLING_EMAIL>
      <DELIVERY_COMPANY_NAME>Zynk Software</DELIVERY_COMPANY_NAME>
      <DELIVERY_TITLE>Mr</DELIVERY_TITLE>
      <DELIVERY_FIRSTNAME>John</DELIVERY_FIRSTNAME>
      <DELIVERY_LASTNAME>Smith</DELIVERY_LASTNAME>
      <DELIVERY_ADDRESS1>Office 4</DELIVERY_ADDRESS1>
      <DELIVERY_ADDRESS2>6-8 Charlotte Square</DELIVERY_ADDRESS2>
      <DELIVERY_TOWN>Newcastle-upon-Tyne</DELIVERY_TOWN>
      <DELIVERY_COUNTY>Tyne &amp; Wear</DELIVERY_COUNTY>
      <DELIVERY_COUNTRY_ID>1</DELIVERY_COUNTRY_ID>
      <DELIVERY_COUNTRY>UK - Mainland</DELIVERY_COUNTRY>
      <DELIVERY_COUNTRY_CODE>GB</DELIVERY_COUNTRY_CODE>
      <DELIVERY_POSTCODE>NE1 4XF</DELIVERY_POSTCODE>
      <DELIVERY_TELEPHONE>0191 303 7279</DELIVERY_TELEPHONE>
      <CUSTOMER_ACCOUNT_NUMBER>ZYN001</CUSTOMER_ACCOUNT_NUMBER>
      <CUSTOMER_GROUP />
      <VAT_REGISTRATION_NUMBER />
    </CUSTOMER>
    <PRODUCTS>
      <PRODUCT>
        <ORDER_PRODUCT_ID>12115</ORDER_PRODUCT_ID>
        <PRODUCT_ID>17524</PRODUCT_ID>
        <PARENT_PRODUCT_REFERENCE>OB-HD</PARENT_PRODUCT_REFERENCE>
        <CHILD_PRODUCT_REFERENCE>OB-HD</CHILD_PRODUCT_REFERENCE>
        <PRODUCT_REFERENCE>OB-HD</PRODUCT_REFERENCE>
        <MODEL />
        <CHILD_PRODUCT_MODEL />
        <EAN />
        <MANUFACTURER_NAME>Genware</MANUFACTURER_NAME>
        <TITLE>Pizza Oven Brush Handle</TITLE>
        <SUMMARY />
        <CATEGORIES>
          <CATEGORY_LEVEL_1>Cleaning Equipment</CATEGORY_LEVEL_1>
          <CATEGORY_LEVEL_2>Cleaning &amp; Hygiene</CATEGORY_LEVEL_2>
          <CATEGORY_LEVEL_3>Sponges &amp; Scourers</CATEGORY_LEVEL_3>
        </CATEGORIES>
        <QUANTITY>2</QUANTITY>
        <PRICE_INC>5.244</PRICE_INC>
        <PRICE_EX>4.37</PRICE_EX>
        <PRICE_VAT>0.874</PRICE_VAT>
        <DISCOUNT_PRICE_INC>0</DISCOUNT_PRICE_INC>
        <DISCOUNT_PRICE_EX>0</DISCOUNT_PRICE_EX>
        <DISCOUNT_PRICE_VAT>0</DISCOUNT_PRICE_VAT>
        <TAX_RATE>20</TAX_RATE>
        <PERSONALISATIONS />
        <COMPONENTS />
        <ACTIVE>Y</ACTIVE>
        <WEIGHT>0.33</WEIGHT>
        <PICK_LOCATION>NEV</PICK_LOCATION>
      </PRODUCT>
    </PRODUCTS>
    <PAYMENT>
      <PAYMENT_AMOUNT>16.49</PAYMENT_AMOUNT>
      <PAYMENT_DATE>2018-07-08 10:01:05</PAYMENT_DATE>
      <PAYMENT_TYPE>Credit or Debit Card</PAYMENT_TYPE>
      <CARD_HOLDER>Zynk Software</CARD_HOLDER>
      <AUTH_CODE>123456</AUTH_CODE>
      <SECURITY_REFERENCE>FB5DD57FBCDD9948B77C64357B76BBCDE2E3D38FD</SECURITY_REFERENCE>
      <TRANSACTION_REFERENCE>1234567890</TRANSACTION_REFERENCE>
      <CV2_AVS />
      <NOTES>9: The payment has been accepted.</NOTES>
    </PAYMENT>
    <TRANSACTION_BREAKDOWN>
      <PAYMENT>
        <PAYMENT_AMOUNT>16.490</PAYMENT_AMOUNT>
        <PAYMENT_DATE>2018-07-08 10:01:05</PAYMENT_DATE>
        <PAYMENT_TYPE>Credit or Debit Card</PAYMENT_TYPE>
        <CARD_HOLDER>Zynk Software</CARD_HOLDER>
        <AUTH_CODE>123456</AUTH_CODE>
        <SECURITY_REFERENCE>FB5DD57FBCDD9948B77C64357B76BBCDE2E3D38FD</SECURITY_REFERENCE>
        <TRANSACTION_REFERENCE>1234567890</TRANSACTION_REFERENCE>
        <CV2_AVS />
        <NOTES>9: The payment has been accepted.</NOTES>
      </PAYMENT>
    </TRANSACTION_BREAKDOWN>
    <DISCOUNTS>
      <DISCOUNT>
        <ID>36</ID>
        <CODE />
        <NAME>Genware £5 Carriage</NAME>
        <DISCOUNT_EX_VAT>1.250</DISCOUNT_EX_VAT>
        <DISCOUNT_INC_VAT>1.500</DISCOUNT_INC_VAT>
        <DISCOUNT_VAT>0.250</DISCOUNT_VAT>
      </DISCOUNT>
    </DISCOUNTS>
  </WEB_ORDER>
</WEB_ORDERS>
```
