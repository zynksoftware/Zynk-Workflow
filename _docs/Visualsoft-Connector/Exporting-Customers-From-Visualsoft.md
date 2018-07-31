---
slug: exporting-customers-from-visualsoft
title: Exporting Customers from Visualsoft
---
This task will export customers from Visualsoft in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Visualsoft connection to use. See the [Connecting to Visualsoft](connecting-to-visualsoft) article if you require more information on how to create/manage connections.

### Date Modified
_Required_  
When the 'Export Type' setting is set to 'Modified', only customers updated after this date will be exported. This date will update automatically each time the task runs.

### Export Detailed
_Required_  
Set to true to export detailed information about each record, or false to export a summary.

### Export Type
_Required_  
Choose which records should be exported. The available options are:

* __Modified__ - Only customers created/updated after the date shown in the 'Date Modified' setting will be exported.
* __LookupById__ - Only customers with the IDs specified in the 'Lookup Value' setting will be exported.
* __LookupByAccountNumber__ - Only customers with the account number specified in the 'Lookup Value' setting will be exported.
* __LookupByName__ - Only customers with the name specified in the 'Lookup Value' setting will be exported.
* __LookupByEmail__ - Only customers with the email address specified in the 'Lookup Value' setting will be exported.

### Lookup Value
_Optional_  
When the 'Export Type' setting is set to LookupById, LookupByAccountNumber, LookupByName or LookupByEmail, specify the value to search for here. When using the LookupById option, you can specify multiple IDs by providing a comma separated list.

When the 'Export Type' setting is set to Modified, any value specified here will be ignored.

### Output File
_Required_  
The name of the file to export the customers to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<CUSTOMERS xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <CUSTOMER>
    <CUSTOMER_ID>5642</CUSTOMER_ID>
    <WEBSITE_ID>1</WEBSITE_ID>
    <CUSTOMER_ACCOUNT_NUMBER>ZYN001</CUSTOMER_ACCOUNT_NUMBER>
    <EMAIL_ADDRESS>support@zynk.com</EMAIL_ADDRESS>
    <DATE_OF_BIRTH />
    <CUSTOMER_OCCUPATION />
    <HEARD_ABOUT />
    <CUSTOMER_NOTES />
    <IS_EXPRESS_CUSTOMER>N</IS_EXPRESS_CUSTOMER>
    <ADDRESSES>
      <ADDRESS>
        <CUSTOMER_TITLE>Mr</CUSTOMER_TITLE>
        <CUSTOMER_FIRSTNAME>John</CUSTOMER_FIRSTNAME>
        <CUSTOMER_LASTNAME>Smith</CUSTOMER_LASTNAME>
        <COMPANY_NAME>Zynk Software</COMPANY_NAME>
        <ADDRESS_LINE_1>Office 4</ADDRESS_LINE_1>
        <ADDRESS_LINE_2>6-8 Charlotte Square</ADDRESS_LINE_2>
        <TOWN>Newcastle-upon-Tyne</TOWN>
        <COUNTY>Type &amp; Wear</COUNTY>
        <POSTCODE>NE1 4XF</POSTCODE>
        <COUNTRY_ISO_CODE>GB</COUNTRY_ISO_CODE>
        <COUNTRY_NAME>UK - Mainland</COUNTRY_NAME>
        <TELEPHONE>0191 303 7279</TELEPHONE>
        <MOBILE></MOBILE>
        <IS_DEFAULT>Y</IS_DEFAULT>
        <ADDRESS_ID>1</ADDRESS_ID>
      </ADDRESS>
    </ADDRESSES>
    <EWALLET>
      <CURRENT_BALANCE>0</CURRENT_BALANCE>
      <LOGS />
    </EWALLET>
    <DATES>
      <DATE_REGISTERED>2018-06-13 22:45:45</DATE_REGISTERED>
      <DATE_LAST_LOGIN>2018-06-13 22:45:45</DATE_LAST_LOGIN>
      <DATE_LAST_MODIFIED>2018-06-21 09:07:03</DATE_LAST_MODIFIED>
      <DATE_EMAIL_OPT_IN>2018-06-13 22:45:45</DATE_EMAIL_OPT_IN>
    </DATES>
    <OPT_INS>
      <EMAIL>No</EMAIL>
      <POST>No</POST>
      <SMS>No</SMS>
      <LOYALTY>Us</LOYALTY>
    </OPT_INS>
    <CUSTOMER_GROUP_ID>0</CUSTOMER_GROUP_ID>
    <CUSTOMER_GROUP_NAME />
    <CURRENT_BALANCE />
    <CREDIT_LIMIT />
    <LOCK_TO_TRADE_ONLY>N</LOCK_TO_TRADE_ONLY>
    <CUSTOMER_TYPE>BUSINESS</CUSTOMER_TYPE>
  </CUSTOMER>
</CUSTOMERS>
```
