---
slug: importing-stock-levels-into-visualsoft
title: Importing Stock Levels into Visualsoft
---
This task will update stock levels in Visualsoft. See below for a sample input file.

Please note that the task can't update products where the stock level is set to infinite.

## Settings
### Connection
_Required_  
The Visualsoft connection to use. See the [Connecting to Visualsoft](connecting-to-visualsoft) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to save failed stock levels to. The data will be written in the same format as the input file.

### Input File
_Required_  
The XML file containing the stock levels to import into Visualsoft.

### Success File
_Required_  
The XML file to save successful stock levels to. The data will be written in the same format as the input file.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. Multiple stock levels are supported within the same file.
```xml
<?xml version="1.0" encoding="utf-8"?>
<STOCK_LEVELS>
  <STOCK_LEVEL>
    <PRODUCT_REFERENCE>OB-HD</PRODUCT_REFERENCE>
    <QUANTITY>10</QUANTITY>
  </STOCK_LEVEL>
</STOCK_LEVELS>
```
