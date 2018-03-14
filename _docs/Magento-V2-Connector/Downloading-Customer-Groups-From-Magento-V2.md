---
slug: downloading-customer-groups-from-magento-v2
redirect_from: "/article/downloading-customer-groups-from-magento-v2"
title: Downloading Customer Groups From Magento V2
---
This task will download customer groups from Magento in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

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
The name of the file to export the customer groups to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfGroup xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Group>
    <id>2</id>
    <code>Wholesale</code>
    <tax_class_id>3</tax_class_id>
    <tax_class_name>Retail Customer</tax_class_name>
  </Group>
</ArrayOfGroup>
```
