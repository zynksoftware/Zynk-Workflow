---
slug: exporting-price-bands-from-sage-200
redirect_from: "/article/427-exporting-price-bands-from-sage-200"
title: Exporting Price Bands from Sage 200
---
This task will export new, modified or all price bands in [Sage 200 XML](sage-200-xml) format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Characters To Cleanse
_Optional_  
A list of characters to remove from the output file. Use this if your Sage data contains characters that are not valid for XML documents (e.g. 	`&#x0;`).

### Export Settings
_Optional_  

 * **Date Created** - Used when exporting new records. Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.
 * **Op Lock** - Used when exporting modified records. Only records where the Op Lock is greater than this value will be exported. The value will update automatically each time the task runs.
 
### Query Settings
_Optional_  

 * **Columns** - Used to enter the column names to export from the Sage database. Be sure to include the table name eg. `[SLCustomerAccount].[CustomerAccountNumber]`
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported. 
 
### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The file to save the exported records to, in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <PriceLists>
    <PriceList AllRecords="false">
      <UniqueId>1008</UniqueId>
      <Name>Standard</Name>
      <Reference>Standard</Reference>
      <Currency>GBP</Currency>
      <Type>PriceList</Type>
      <Prices>
        <Price Action="Upsert">
          <UniqueId>6689</UniqueId>
          <DiscountType>Fixed</DiscountType>
          <StockCode>PROD001</StockCode>
          <StoredPrice>34.2</StoredPrice>
          <Value>0</Value>
          <ExternalReference>PROD001</ExternalReference>
          <BaseQty xsi:nil="true" />
          <QtyBreak xsi:nil="true" />
          <DiscountAmountValue xsi:nil="true" />
          <DiscountPercentValue xsi:nil="true" />
        </Price>
        <Price Action="Upsert">
          <UniqueId>6430</UniqueId>
          <DiscountType>Fixed</DiscountType>
          <StockCode>PROD002</StockCode>
          <StoredPrice>220.8083</StoredPrice>
          <Value>0</Value>
          <ExternalReference>PROD002</ExternalReference>
          <BaseQty xsi:nil="true" />
          <QtyBreak xsi:nil="true" />
          <DiscountAmountValue xsi:nil="true" />
          <DiscountPercentValue xsi:nil="true" />
        </Price>
      </Prices>
    </PriceList>
    <PriceList AllRecords="false">
      <UniqueId>1009</UniqueId>
      <Name>Trade</Name>
      <Reference>Trade</Reference>
      <Currency>GBP</Currency>
      <Type>PriceList</Type>
      <Prices>
        <Price Action="Upsert">
          <UniqueId>7021</UniqueId>
          <DiscountType>Fixed</DiscountType>
          <StockCode>PROD001</StockCode>
          <StoredPrice>25.2</StoredPrice>
          <Value>0</Value>
          <ExternalReference>PROD001</ExternalReference>
          <BaseQty xsi:nil="true" />
          <QtyBreak xsi:nil="true" />
          <DiscountAmountValue xsi:nil="true" />
          <DiscountPercentValue xsi:nil="true" />
        </Price>
        <Price Action="Upsert">
          <UniqueId>6984</UniqueId>
          <DiscountType>Fixed</DiscountType>
          <StockCode>PROD002</StockCode>
          <StoredPrice>160.8083</StoredPrice>
          <Value>0</Value>
          <ExternalReference>PROD002</ExternalReference>
          <BaseQty xsi:nil="true" />
          <QtyBreak xsi:nil="true" />
          <DiscountAmountValue xsi:nil="true" />
          <DiscountPercentValue xsi:nil="true" />
        </Price>
      </Prices>
    </PriceList>
  </PriceLists>
</Company>
```