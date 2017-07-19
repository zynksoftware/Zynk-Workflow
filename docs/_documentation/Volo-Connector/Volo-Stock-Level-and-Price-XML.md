---
slug: volo-stock-level-and-price-xml
title: Volo Stock Level and Price XML
---
The [Importing Stock Levels and Prices into Volo](importing-stock-levels-and-prices-into-volo) task allows you to update the stock level and price of products in Volo. The XML format required for the Input File is described below. Any fields not documented below are not directly supported with our imports.

Sample XML for updating stock levels and prices:

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

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum. The whole structure of the XML schema is used below as a reference of where fields should be in the object model.

## Product Update
The `<ProductUpdate>` element represents a product and it's new stock level and prices.

| Volo Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | externalId | 7539 | string | 255 | Optional | The ID of the corresponding order from the external system. Used in conjunction with the 'Prevent Reprocessing' setting on the task. |
| Stock Number | stockNumber | 100101 | string | - | Required | The stock number must already exist in Volo. |
| - | stockLevel | - | stockLevel | - | Optional | The new stock level for the product. See below for details. |
| - | prices | - | array | - | Optional | The list of prices for the product. See below for details. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductUpdates xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ProductUpdate>
    <externalId>7539</externalId>
    <stockNumber>100101</stockNumber>
    <stockLevel>
      <!-- See below -->
    </stockLevel>
    <prices>
      <!-- See below -->
    </prices>
  </ProductUpdate>
</ProductUpdates>
```

## Stock Level
The `<stockLevel>` element represents the new stock level to set in Volo. It will appear in Volo in the 'Stock' section on the 'Details' tab when viewing a product. It doesn't need to be provided if you are just updating the prices.

| Volo Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Location | location | Newcastle | string | - | Optional |  |
| Quantity | quantity | 20 | int | - | Optional |  |
| Type of Adjustment | stockUpdateType | STOCK_CHECK | enum | - | Optional | Available values: 'DELIVERY', 'STOCK_CHECK', 'STOCK_CHECK_ADJUST_COMMITTED' |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductUpdates xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ProductUpdate>
    <stockLevel>
      <location>Newcastle</location>
      <quantity>20</quantity>
      <stockUpdateType>STOCK_CHECK</stockUpdateType>
    </stockLevel>
  </ProductUpdate>
</ProductUpdates>
```

## Price
The `<price>` element represents a price for the product in Volo. It will appear in Volo in the 'Prices' section on the 'Details' tab when viewing a product. One or more prices can be provided within the `<prices>` collection. Prices don't need to be provided if you are just updating the stock level.

| Volo Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Price | name | RRP | enum | - | Required | Available values: 'EBAY_BUY_NOW_PRICE', 'EBAY_INVENTORY_PRICE', 'RRP', 'AMAZON_PRICE', 'PLAY_PRICE' |
| Amount | value | 20 | int | - | Required |  |
| - | accountName | - | string | - | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductUpdates xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ProductUpdate>
    <prices>
      <price>
        <name>RRP</name>
        <value>10.99</value>
        <accountName></accountName>
      </price>
    </prices>
  </ProductUpdate>
</ProductUpdates>
```
