---
slug: downloading-customers-from-magento-v2
redirect_from: "/article/766-downloading-customers-from-magento"
title: Downloading Customers From Magento V2
---
This task will download customers from Magento in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Download Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'All', only customers created after this date will be downloaded. This date will update automatically each time the task runs.

### Download Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only customers updated after this date will be downloaded. This date will update automatically each time the task runs.

### Download Settings > Export Modified, New or All Records
_Required_  
Choose which records should be downloaded. The available options are:

* __Modified__ - Only records updated after the date shown in the 'Date Modified' setting will be downloaded.
* __New__ - Only records created after the date shown in the 'Date Created' setting will be downloaded.
* __All__ - All records will be downloaded, regardless of when they were created or updated.

### Filter Groups
_Optional_  
The filtering to apply to the records. Only records which match the criteria specified will be downloaded.

Filters are arranged into groups. The individual filters within a group will be combined using the OR operator. Groups of filters are combined using the AND operator.

### Filter Groups > Filter > Condition
_Optional_  
The following types of filter are available:

* __Equal__ - Returns records where the field matches the specified value.
* __NotEqual__ - Returns records where the field does not match the specified value.
* __Like__ - Returns records where the field contains the specified value.
* __In__ - Returns records where the field matches one of the specified values.
* __NotIn__ - Returns records where the field does not match one of the specified values.
* __Null__ - Returns records where the field does not have a value.
* __NotNull__ - Returns records where the field has a value.
* __GreaterThan__ - Returns records where the field is greater than the specified value.
* __LessThan__ - Returns records where the field is less than the specified value.
* __GreaterThanOrEqual__ - Returns records where the field is greater than or equal to the specified value.
* __LessThanOrEqual__ - Returns records where the field is less than or equal to the specified value.

### Filter Groups > Filter > Field
_Optional_  
The name of the field the filter is to be based upon. The name should match the API field name, as seen in the output file.

### Filter Groups > Filter > Value
_Optional_  
The value the filter is to be based upon. This is not required when using the 'Null' or 'NotNull' condition type.

### Page Size
_Required_  
The number of records to include in each page of results. Defaults to 50. Increasing this value will increase the speed of the download, but will consume more memory.

### Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'default'.

### Output File
_Required_  
The name of the file to export the customers to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <id>1</id>
    <group_id>1</group_id>
    <created_at>2016-02-01T10:57:13</created_at>
    <default_billing>1</default_billing>
    <default_shipping>1</default_shipping>
    <created_in>Default Store View</created_in>
    <dob xsi:nil="true" />
    <email>roni_cost@example.com</email>
    <firstname>Veronica</firstname>
    <lastname>Costello</lastname>
    <gender>0</gender>
    <store_id>1</store_id>
    <website_id>1</website_id>
    <addresses>
      <address>
        <id>1</id>
        <customer_id>1</customer_id>
        <region>
          <region_code>Michigan</region_code>
          <region>Michigan</region>
          <region_id>0</region_id>
        </region>
        <region_id>0</region_id>
        <country_id>US</country_id>
        <street>
          <string>6146 Honey Bluff Parkway</string>
        </street>
        <telephone>(555) 229-3326</telephone>
        <postcode>49628-7978</postcode>
        <city>Calder</city>
        <firstname>Veronica</firstname>
        <lastname>Costello</lastname>
        <default_billing>true</default_billing>
        <default_shipping>true</default_shipping>
      </address>
      <address>
        <id>2</id>
        <customer_id>1</customer_id>
        <region>
          <region_code>Michigan</region_code>
          <region>Michigan</region>
          <region_id>0</region_id>
        </region>
        <region_id>0</region_id>
        <country_id>US</country_id>
        <street>
          <string>6146 Honey Bluff Parkway</string>
        </street>
        <telephone>(555) 229-3326</telephone>
        <postcode>49628-7978</postcode>
        <city>Calder</city>
        <firstname>Veronica</firstname>
        <lastname>Costello</lastname>
        <default_billing xsi:nil="true" />
        <default_shipping xsi:nil="true" />
      </address>
      <address>
        <id>3</id>
        <customer_id>1</customer_id>
        <region>
          <region_code>Michigan</region_code>
          <region>Michigan</region>
          <region_id>0</region_id>
        </region>
        <region_id>0</region_id>
        <country_id>US</country_id>
        <street>
          <string>6146 Honey Bluff Parkway</string>
        </street>
        <telephone>(555) 229-3326</telephone>
        <postcode>49628-7978</postcode>
        <city>Calder</city>
        <firstname>Veronica</firstname>
        <lastname>Costello</lastname>
        <default_billing xsi:nil="true" />
        <default_shipping xsi:nil="true" />
      </address>
    </addresses>
    <disable_auto_group_change>0</disable_auto_group_change>
    <updated_at>2016-02-01T11:00:52</updated_at>
  </Customer>
</ArrayOfCustomer>
```
