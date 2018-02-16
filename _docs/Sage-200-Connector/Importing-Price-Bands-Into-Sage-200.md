---
slug: importing-price-bands-into-sage-200
redirect_from: "/article/920-importing-price-bands-into-sage-200"
title: Importing Price Bands Into Sage 200
---
This task will import create new and update existing price bands and selling prices in Sage 200, from an XML file formatted in Zynk XML format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed price bands in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported price bands in Zynk XML format.

### New Selling Price Terms
_Required_  
Choose the default selling price to use for each product. This setting only applies when creating a new price band in Sage, and a price hasn't been provided for a product in the input file. The following options are available:	

 * **SetToZero** - The price for all products not in the input file will be set to 0.
 * **LinkToStandardPrice** - The price for all products not in the input file will be linked to the product's standard price.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a price band is shown below. See our [Sage 200 Price Band XML](sage-200-price-band-xml) for more details on the Zynk XML Price Lists format for Sage 200.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PriceLists>
    <PriceList AllRecords="false">
      <Id>1001</Id>
      <Name>Trade</Name>
      <Currency>GBP</Currency>
      <Type>PriceList</Type>
      <Prices>
        <Price>
          <StockCode>ABBuiltIn/15/0/2</StockCode>
          <StoredPrice>249.95</StoredPrice>
        </Price>
        <Price>
          <StockCode>ABBuiltIn/15/1/2</StockCode>
          <StoredPrice>259.95</StoredPrice>
        </Price>
      </Prices>
    </PriceList>
  </PriceLists>
</Company>	
```