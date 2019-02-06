---
slug: downloading-customers-from-bigcommerce-v3
title: Downloading Customers from BigCommerce V3
---
This task will download customers registered on your BigCommerce store to an XML file.

## Settings
### Connection
_Required_  
The BigCommerce connection to use.See the [Connecting to BigCommerce V3](connecting-to-bigcommerce-v3) article if you require more information on how to create/manage connections.

### Export Addresses
_Required_  
Set to true to include all customer addresses in the output file, or set to false to only include main customer data.  Defaults to True.

### Export Settings > Date Created
_Required_  
When the 'Export Type' is set to New, only records created after this date will be downloaded.  The date will update automatically each time the task runs based on the data returned.

### Export Settings > Date Modified
_Required_  
When the 'Export Type' is set to Modified, only records updated after this date will be downloaded.  The date will update automatically each time the task runs based on the data returned.

### Export Settings > Export Type
_Required_  
Used to choose which records should be included in the download.  The available options are: -

 - **New** - Only records created since the task last ran will be downloaded
 - **Modified** - Only records created or updated since the task last ran will be downloaded
 - **All** - All records will be downloaded, regardless of whether or not they have been updated since the task last ran

### Output File
_Required_  
The name of the XML file to export the data to (e.g. big_commerce_export_customers.xml).

### Page Size
_Required_  
The number of records returned per page of the request.  Defaults to 50.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below showing the customer 'Zynk Software Limited'.  For detailed documentation on the fields please see the [BigCommerce Dev Center](https://developer.bigcommerce.com/api-reference/customer-subscribers/customers-api/customers/getcustomers).

```xml
<?xml version="1.0" encoding="utf-8"?>
<customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customer>
    <id>1</id>
    <zynk_external_id />
    <date_created>2013-08-09T14:04:01+01:00</date_created>
    <date_modified>2019-01-15T17:11:38+00:00</date_modified>
    <company>Zynk Software Limited</company>
    <first_name>Joe E</first_name>
    <last_name>Harrison</last_name>
    <email>joe.harrison@zynk.com</email>
    <phone>0845 123 2920</phone>
    <store_credit>0.0000</store_credit>
    <registration_ip_address>78.86.222.163</registration_ip_address>
    <customer_group_id>0</customer_group_id>
    <notes />
    <tax_exempt_category />
    <accepts_marketing>true</accepts_marketing>
    <addresses>
      <resource>/customers/1/addresses</resource>
      <url>https://api.bigcommerce.com/stores/v5k4i/v2/customers/1/addresses</url>
      <records>
        <address>
          <id>1</id>
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
        </address>
      </records>
    </addresses>
    <reset_pass_on_login>false</reset_pass_on_login>
  </customer>
</customers>
```