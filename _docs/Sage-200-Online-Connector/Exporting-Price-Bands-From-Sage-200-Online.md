---
slug: exporting-price-bands-from-sage-200-online
redirect_from: "/article/exporting-price-bands-from-sage-200-online"
title: Exporting Price Bands From Sage 200 Online
---
This task will download all price bands from Sage 200 Online to an XML file.

## Settings
### Sage 200 Online Connection
_Required_  
The connection to Sage 200 Online to use. See the [Connecting to Sage 200 Online](connecting-to-sage-200-online) article if you require more information on how to create/manage connections.

### Filter
_Optional_  
Allows a filter to be set to limit the data that is returned. For example, you can just return the standard price band using: `price_band_name eq 'Standard'`

Sage 200 Online uses the OData protocol, and expects the filter to be specified in this format. You can find more information on OData filters [here](http://www.odata.org/getting-started/basic-tutorial/#queryData).

### Output File
_Required_  
The name of the file to save the downloaded records to.

### Page Size
_Required_  
The number of records to include in each page of results downloaded from Sage. Increasing this value will speed up the download, but will use more memory. Defaults to 50.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductPriceViews xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ProductPriceView>
    <product_price_id>15556</product_price_id>
    <product_id>15536</product_id>
    <product_code>TEST001</product_code>
    <product_name>Test Product</product_name>
    <product_stock_unit_name>Each</product_stock_unit_name>
    <price_band_id>1001</price_band_id>
    <price_band_name>Standard</price_band_name>
    <product_price_use_standard>false</product_price_use_standard>
    <product_price_price>10.00000</product_price_price>
    <currency_id>1</currency_id>
    <currency_name>Pound Sterling</currency_name>
    <currency_symbol>£</currency_symbol>
  </ProductPriceView>
</ProductPriceViews>
```
