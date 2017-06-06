---
slug: downloading-attribute-options-from-magento
redirect_from: "/article/258-downloading-attribute-options-from-magento"
title: Downloading Attribute Options from Magento
---
This task will download all option values for a selected product attribute from Magento in Magento XML format.

## Settings
### Attribute
_Required_  
The attribute code (eg 'colour').

### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the option values to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file when downloading the options for a 'colour' attribute:
```xml
<?xml version="1.0"?>
<ArrayOfProductAttributeOption>
  <ProductAttributeOption>
    <value>3</value>
    <label>Blue</label>
  </ProductAttributeOption>
  <ProductAttributeOption>
    <value>5</value>
    <label>Green</label>
  </ProductAttributeOption>
  <ProductAttributeOption>
    <value>6</value>
    <label>Red</label>
  </ProductAttributeOption>
  <ProductAttributeOption>
    <value>4</value>
    <label>Yellow</label>
  </ProductAttributeOption>
</ArrayOfProductAttributeOption>
```