---
slug: uploading-tier-prices-to-magento-v2
redirect_from: "/article/774-uploading-tier-prices-to-magento"
title: Uploading Tier Prices to Magento V2
---
 This task will create or update tier prices for products in Magento. See below for a sample input file.

The task uses the `<sku>`, `<customer_group_name>`, and `<qty>` elements to check if the tier price already exists. If a match is found the existing tier price will be updated, otherwise a new tier price will be created.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

## Fail File
_Required_  
The XML file to save failed tier price uploads to. The data will be written in the same format as the input file.

## Input File
_Required_  
The XML file containing the tier prices to upload in Magento.

## Success File
_Required_  
The XML file to save successful tier price uploads to. The data will be written in the same format as the input file.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfTierPrice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <TierPrice>
    <sku>24-MB01</sku>
    <customer_group_name>Wholesale</customer_group_name>
    <qty>3</qty>
    <value>29.99</value>
  </TierPrice>
  <TierPrice>
    <sku>24-MB01</sku>
    <customer_group_name>Wholesale</customer_group_name>
    <qty>10</qty>
    <value>25.99</value>
  </TierPrice>
  <TierPrice>
    <sku>24-MB01</sku>
    <customer_group_name>ALL GROUPS</customer_group_name>
    <qty>3</qty>
    <value>49.99</value>
  </TierPrice>
</ArrayOfTierPrice>
```
