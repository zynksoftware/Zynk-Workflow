---
slug: exporting-price-lists-from-sage-50-uk
redirect_from: "/article/397-exporting-price-lists-from-sage-50-uk"
title: Exporting Price Lists from Sage 50 UK
---
This task will export price lists from Sage 50 in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export All
_Required_  
Set this to False to export records modified since the last export, or set to True to export all records every time it runs.

### Recalculate Prices
_Required_  
Set this to True to recalculate the prices written to the export file, or False to export the stored price directly from Sage.

### Output File
_Required_  
The name of the file to export to. Data is exported in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <PriceLists>
        <PriceList AllRecords="false">
            <Name>Public Price List</Name>
            <Reference>PUBLIC</Reference>
            <Currency>GBP</Currency>
            <Type>PriceList</Type>
            <Prices>
                <Price Action="Upsert">
                    <DiscountType>DecreasePercent</DiscountType>
                    <StockCode>BOARD001</StockCode>
                    <StoredPrice>0</StoredPrice>
                    <Value>2</Value>
                    <ExternalReference>PPUBLIC  BOARD001</ExternalReference>
                    <BaseQty xsi:nil="true" />
                    <QtyBreak xsi:nil="true" />
                    <DiscountAmountValue xsi:nil="true" />
                    <DiscountPercentValue xsi:nil="true" />
                </Price>
                <Price Action="Upsert">
                    <DiscountType>DecreasePercent</DiscountType>
                    <StockCode>BOARD002</StockCode>
                    <StoredPrice>0</StoredPrice>
                    <Value>2</Value>
                    <ExternalReference>PPUBLIC  BOARD002</ExternalReference>
                    <BaseQty xsi:nil="true" />
                    <QtyBreak xsi:nil="true" />
                    <DiscountAmountValue xsi:nil="true" />
                    <DiscountPercentValue xsi:nil="true" />
                </Price>
                <Price Action="Upsert">
                    <DiscountType>DecreasePercent</DiscountType>
                    <StockCode>BOOKS001</StockCode>
                    <StoredPrice>0</StoredPrice>
                    <Value>2</Value>
                    <ExternalReference>PPUBLIC  BOOKS001</ExternalReference>
                    <BaseQty xsi:nil="true" />
                    <QtyBreak xsi:nil="true" />
                    <DiscountAmountValue xsi:nil="true" />
                    <DiscountPercentValue xsi:nil="true" />
                </Price>
                <Price Action="Upsert">
                    <DiscountType>DecreasePercent</DiscountType>
                    <StockCode>BOOKS002</StockCode>
                    <StoredPrice>0</StoredPrice>
                    <Value>2</Value>
                    <ExternalReference>PPUBLIC  BOOKS002</ExternalReference>
                    <BaseQty xsi:nil="true" />
                    <QtyBreak xsi:nil="true" />
                    <DiscountAmountValue xsi:nil="true" />
                    <DiscountPercentValue xsi:nil="true" />
                </Price>
                <Price Action="Upsert">
                    <DiscountType>DecreasePercent</DiscountType>
                    <StockCode>BOOKS003</StockCode>
                    <StoredPrice>0</StoredPrice>
                    <Value>2</Value>
                    <ExternalReference>PPUBLIC  BOOKS003</ExternalReference>
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