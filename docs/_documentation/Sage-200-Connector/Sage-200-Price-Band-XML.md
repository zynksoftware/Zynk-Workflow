---
slug: sage-200-price-band-xml
title: Sage 200 Price Band XML
---
The Import Price Bands task allows you to create and update price bands in Sage 200. Price bands are matched based on name, if no match is found a new price band will be created, otherwise the existing one will be updated. This task is available in Zynk v2.6 and above.  

Any Sage fields not documented below are not currently supported with our imports.  

Sample import file for creating a price band:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PriceLists>
    <PriceList>
      <Name>Trade</Name>
      <Currency>GBP</Currency>
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

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create/update a price band.  The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Price Band Details
Price bands are matched based on the name provided in the XML. If no match is found in Sage, a new price band will be created, otherwise the existing one will be updated.

|  XML Field | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | N/A | 12345 | string | 255 | Optional | The Id provided will be stored in [Truth Storage](storage), and will be outputted by [Exporting Price Lists from Sage 200](exporting-price-bands-from-sage-200). |
| Name | Name | Trade | string | 20 | Required | Only used if an AccountReference is not provided. |
| Currency | Currency | GBP | string | 3 | Optional | This field is required when creating a new price band. The currency of existing price bands can't be changed. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PriceLists>
    <PriceList>
      <Id>12345</Id>
      <Name>Trade</Name>
      <Currency>GBP</Currency>
    </PriceList>
  </PriceLists>
</Company>
```

## Prices For Price Band
When updating an existing price band, any products which don't have a price specified in the XML won't be updated. When creating a new price band, they will be given a default value based on the setting on the task.

|  XML Field | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| StockCode | Code | ABBuiltIn/15/0/2 | string | 30 | Required | The stock code provided must already exist in Sage. |
| StoredPrice | Price | 249.95 | decimal | - | Required |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PriceLists>
    <PriceList>
      <Prices>
        <Price>
          <StockCode>ABBuiltIn/15/0/2</StockCode>
          <StoredPrice>249.95</StoredPrice>
        </Price>
      </Prices>
    </PriceList>
  </PriceLists>
</Company>
```