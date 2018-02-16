---
slug: downloading-customer-groups-from-magento
title: Downloading Customer Groups from Magento
---
This task will download all customer groups from Magento in XML format. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the customers to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomerGroup xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <CustomerGroup>
    <customer_group_id>0</customer_group_id>
    <customer_group_code>NOT LOGGED IN</customer_group_code>
  </CustomerGroup>
  <CustomerGroup>
    <customer_group_id>1</customer_group_id>
    <customer_group_code>General</customer_group_code>
  </CustomerGroup>
  <CustomerGroup>
    <customer_group_id>2</customer_group_id>
    <customer_group_code>Wholesale</customer_group_code>
  </CustomerGroup>
</ArrayOfCustomerGroup>
```