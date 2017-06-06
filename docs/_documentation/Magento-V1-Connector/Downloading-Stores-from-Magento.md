---
slug: downloading-stores-from-magento
title: Downloading Stores from Magento
---
This task will download all stores from Magento in XML format. See below for a sample output file.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the stores to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfStore xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Store>
    <store_id>1</store_id>
    <code>default</code>
    <website_id>1</website_id>
    <group_id>1</group_id>
    <name>Default Store View</name>
    <sort_order>0</sort_order>
    <is_active>1</is_active>
  </Store>  
  <Store>
    <store_id>2</store_id>
    <code>amazon_uk</code>
    <website_id>1</website_id>
    <group_id>2</group_id>
    <name>Amazon UK</name>
    <sort_order>0</sort_order>
    <is_active>0</is_active>
  </Store>
  <Store>
    <store_id>3</store_id>
    <code>amazon_germany</code>
    <website_id>1</website_id>
    <group_id>3</group_id>
    <name>Amazon DE</name>
    <sort_order>2</sort_order>
    <is_active>0</is_active>
  </Store>
</ArrayOfStore>
```