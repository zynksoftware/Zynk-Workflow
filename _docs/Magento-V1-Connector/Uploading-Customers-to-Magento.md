---
slug: uploading-customers-to-magento
redirect_from: "/article/267-uploading-customers-to-magento"
title: Uploading Customers to Magento
---
This task will upload new and update existing customers in Magento. The input file should be in Magento XML format. If an existing customer_id or email is provided in the input file, the existing customer will be updated in Magento, otherwise a new customer will be created.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed customer uploads to.

### Input File
_Required_  
The XML file containing the customers to upload to Magento. Note that you only need to provide values for fields you want to update.

### Success File
_Required_  
The XML file to output successful customer uploads to.

### Only Update Old Records
_Required_  
Set to True to only update customers in Magento which have not been modified more recently than those provided in the input file (based on the updated_at date).

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Standard Price List
_Optional_  
The name of the default customer group to assign to customers who don't have a group_id provided in the input file.

### Upload Address Book
_Required_  
Set to True to upload the address book for the customer (if provided in the input file).

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0"?>
<ArrayOfCustomer>
  <Customer>
    <firstname>Andrew</firstname>
    <group_id>1</group_id>
    <suffix />
    <customer_id>1</customer_id>
    <default_billing>9</default_billing>
    <prefix>Mr</prefix>
    <store_id>0</store_id>
    <lastname>Snape</lastname>
    <default_shipping>9</default_shipping>
    <website_id>1</website_id>
    <middlename />
    <email>andrew.snape@internetware.co.uk</email>
    <default_billing_address>
      <city>Newcastle</city>
      <firstname>Andrew</firstname>
      <updated_at>2012-01-13 11:03:34</updated_at>
      <is_default_shipping>true</is_default_shipping>
      <country_id>GB</country_id>
      <company>Internetware</company>
      <postcode>NE1 4XF</postcode>
      <prefix>Mr</prefix>
      <region>Tyne and Wear</region>
      <lastname>Snape</lastname>
      <is_default_billing>true</is_default_billing>
      <fax>0845 123 2921</fax>
      <street>Newcastle Business Centre
6 Charlotte Square</street>
      <middlename />
      <telephone>0845 123 2920</telephone>
      <created_at>2012-01-13 09:49:18</created_at>
      <region_id>0</region_id>
    </default_billing_address>
    <default_shipping_address>
      <city>Newcastle</city>
      <firstname>Andrew</firstname>
      <updated_at>2012-01-13 11:03:34</updated_at>
      <is_default_shipping>true</is_default_shipping>
      <country_id>GB</country_id>
      <company>Internetware</company>
      <postcode>NE1 4XF</postcode>
      <prefix>Mr</prefix>
      <region>Tyne and Wear</region>
      <lastname>Snape</lastname>
      <is_default_billing>true</is_default_billing>
      <fax>0845 123 2921</fax>
      <street>Newcastle Business Centre
6 Charlotte Square</street>
      <middlename />
      <telephone>0845 123 2920</telephone>
      <created_at>2012-01-13 09:49:18</created_at>
      <region_id>0</region_id>
    </default_shipping_address>
  </Customer>
</ArrayOfCustomer>
```