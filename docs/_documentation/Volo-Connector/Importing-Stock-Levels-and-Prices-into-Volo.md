---
slug: importing-stock-levels-and-prices-into-volo
title: Importing Stock Levels and Prices into Volo
---
This task will update the stock level and price of existing products in Volo, based on an XML file.

## Settings
### Connection
_Required_  
The Volo connection to use. See the [Connecting to Volo](connecting-to-volo) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any records which fail to import into Volo. Defaults to 'volo_import_stock_levels_and_prices_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the records to import into Volo. Defaults to 'volo_import_stock_levels_and_prices.xml'.

### Success File
_Required_  
The name of the XML file to save any records which were successfully imported into Volo. Defaults to 'volo_import_stock_levels_and_prices_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent records with the same `<externalId>` as a previously imported record from being imported into Volo again.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. See [Volo Stock Level and Price XML](volo-stock-level-and-price-xml) for more detailed information.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductUpdates xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ProductUpdate>
    <stockNumber>100101</stockNumber>
    <stockLevel>
      <location>Newcastle</location>
      <quantity>20</quantity>
      <stockUpdateType>STOCK_CHECK</stockUpdateType>
    </stockLevel>
    <prices>
      <price>
        <name>RRP</name>
        <value>10.99</value>
      </price>
    </prices>
  </ProductUpdate>
</ProductUpdates>
```