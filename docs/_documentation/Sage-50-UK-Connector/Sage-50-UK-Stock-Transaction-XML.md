---
slug: sage-50-uk-stock-transaction-xml
title: Sage 50 UK Stock Transaction XML
---
Import Stock Transactions allows you to create new stock transactions in Sage 50, allowing you to adjust stock levels.  Note that each type will create either a positive or negative adjust, using stock transactions you cannot set an absolute quantity in stock.  Any fields not documented below are not supported with our imports.

Sample XML snippets are provided throughout, these are separated out for clarity and so that the hierarchy of the fields relative to the Company XML object model can be easily identified. A full sample of each of the supported stock transaction types is provided at the bottom of this article.

## Preventing Duplication of Previously Imported Stock Transactions

You can optionally provide an Id for each stock transaction, populating it with the unique identifier of the stock transaction from the external system (where the data originated). Any successfully imported stock transaction Id's will be stored in an internal database associated with the Workflow. The Import Stock Transactions task can then be set to prevent duplicates based on the stored Id's, preventing accidental reprocessing of already imported stock transactions.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1 | string | 4000 | Optional | The Zynk Id of the Sage 200 stock transaction. _See paragraph above for details of how this is used._  |

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>1</Id>
          </StockTransaction>
     </StockTransactions>
</Company>
```

## Stock Transaction Types
You need to provide the StockTransactionType for each stock transaction.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| StockTransactionType | Type | AdjustmentIn | enum | - | Required | The type of stock transaction to create in Sage 50. _See the table below for a list of the available Zynk stock transaction types and the Sage 50 stock transactions that they relate to._ |

### AdjustmentIn - AI	
Equivalent of using the 'Adjustment in' button via the Sage 50 UI.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### AdjustmentOut - AO	
Equivalent of using the 'Adjustment out' button via the Sage 50 UI.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>AdjustmentOut</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### DamagesIn - DI 
Equivalent of using the 'Returns' button via the Sage 50 UI.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>DamagesIn</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### DamagesOut - DO
Equivalent of using the 'Returns' button via the Sage 50 UI. 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>DamagesOut</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### GoodsIn - GI
No equivalent via the Sage 50 UI.  Represents receiving goods on a purchase order.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>GoodsIn</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### GoodsOut - GO
No equivalent via the Sage 50 UI.  Represents despatching goods on a sales order / invoice. 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>GoodsOut</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### MovementIn - MI
Equivalent of using the 'Stock transfer' button via the Sage 50 UI.  Should be used with the matching MovemenOut. 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>MovementIn</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### MovementOut - MO
Equivalent of using the 'Stock transfer' button via the Sage 50 UI.  Should be used with the matching MovementIn.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>MovementOut</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Transfer - MI/MO
Equivalent of using the 'Stock transfer' button via the Sage 50 UI.  Will create the required MI/MO records.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>Transfer</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### WriteOff - WO
Equivalent of using the 'Returns' button via the Sage 50 UI. 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionType>WriteOff</StockTransactionType>
        </StockTransaction>
    </StockTransactions>
</Company>
```

## Stock Transaction Fields
The fields in the table below are shared across all stock transaction types.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| StockCode | Product Code | PROD001 | string | 30 | Required | The Code of the Stock Item in Sage that you would like to create the stock transaction against. |
| StockTransactionDate | Date  | 2016-05-04T00:00:00  | datetime  | -  | Optional  | The date of the stock transaction. Defaults to the date the transaction is imported if not provided. _The date needs to be in XSD format (yyyy-MM-ddTHH:mm:ss), only the date is displayed via the Sage UI._  |
| Reference | Ref. | NE6 STOCK | string | 30 | Optional | An optional reference that can be used to help make the stock transaction in Sage easier to identify. |
| Details | Details | +2 stock | string | 60 | Required | An additional description that can be provided |
| Qty | Qty In / Qty Out | 2 | double | 15, 5 | Required | The amount of stock to adjust in Sage. |
| CostPrice  | Cost Price | 10 | double | - | Optional | Only used for AI, DI, GI, MI and Transfer |
| SalesPrice | Sales Price | 15 | double | - | Optional | Only used for GO. |

```xml
<?xml version="1.0"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+2 stock</Details>
            <Qty>2</Qty>

            <!-- AI, DI, GI and MI Only>
            <!-- <CostPrice>10</CostPrice> -->

            <!-- GO Only -->
            <!-- <SalesPrice>15</SalesPrice> -->
        </StockTransaction>
    </StockTransactions>
</Company>
```

## Transfers - BOM Items
Note we only currently support building top level BOM items.  If a component of the item you are trying to transfer into stock is also a BOM item and there is not enough quantity to fulfil the transfer will fail.

## Success File
Any successfully imported stock transactions will be written out with the Sage assigned transaction number.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| StockTransactionNumber | No | 1 | double | - | - | The Sage assigned transaction number |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <StockTransactionNumber>2</StockTransactionNumber>
        </StockTransaction>
    </StockTransactions>
</Company>
```

## Fail File
Any transactions that fail to import will be written out with a collection of validation errors.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Date | - | 2016-11-03T08:48:37 | datetime | - | - | The date and time the validation error occurred |
| Name | - | Validation | string | - | - |
| Description | - | PROD002 does not have enough free stock to complete this transfer | string | - | - | The validation message |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>>
            <Errors>
                <Error>
                    <Date>2016-11-03T08:48:37.0994209+00:00</Date>
                    <Name>Validation</Name>
                    <Description>PROD002 does not have enough free stock to complete this transfer</Description>
                </Error>
            </Errors>
        </StockTransaction>
    </StockTransactions>
</Company>
```

## Full Samples

### Adjustment In / Out
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>1</Id>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+2 stock</Details>
            <Qty>2</Qty>
            <CostPrice>10</CostPrice>
        </StockTransaction>
        <StockTransaction>
            <Id>2</Id>
            <StockTransactionType>AdjustmentOut</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>-2 stock</Details>
            <Qty>2</Qty>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Damages In / Out

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>3</Id>
            <StockTransactionType>DamagesIn</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+2 stock</Details>
            <Qty>2</Qty>
            <CostPrice>10</CostPrice>
        </StockTransaction>
        <StockTransaction>
            <Id>4</Id>
            <StockTransactionType>DamagesOut</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>-2 stock</Details>
            <Qty>2</Qty>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Goods In / Out

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>5</Id>
            <StockTransactionType>GoodsIn</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+2 stock</Details>
            <Qty>2</Qty>
            <CostPrice>10</CostPrice>
        </StockTransaction>
        <StockTransaction>
            <Id>6</Id>
            <StockTransactionType>GoodsOut</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>-2 stock</Details>
            <Qty>2</Qty>            
            <SalesPrice>15</SalesPrice>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Movement In / Out

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>7</Id>
            <StockTransactionType>MovementOut</StockTransactionType>
            <StockCode>PROD002</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>-2 stock</Details>
            <Qty>2</Qty>
        </StockTransaction>
        <StockTransaction>
            <Id>8</Id>
            <StockTransactionType>MovementIn</StockTransactionType>
            <StockCode>PROD003</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+1 stock</Details>
            <Qty>1</Qty>
            <CostPrice>10</CostPrice>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Transfer

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>9</Id>
            <StockTransactionType>Transfer</StockTransactionType>
            <StockCode>PROD003</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+1 stock</Details>
            <Qty>1</Qty>
            <CostPrice>10</CostPrice>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Write Off

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>10</Id>
            <StockTransactionType>WriteOff</StockTransactionType>
            <StockCode>PROD003</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>-1 stock</Details>
            <Qty>1</Qty>
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Success File

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>1</Id>
            <UniqueId>23</UniqueId>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+2 stock</Details>
            <Qty>2</Qty>
            <CostPrice>10</CostPrice>
            <SalesPrice xsi:nil="true" />
            <StockTransactionNumber>23</StockTransactionNumber>
            <CustomFields />
        </StockTransaction>
        <StockTransaction>
            <Id>2</Id>
            <UniqueId>24</UniqueId>
            <StockTransactionType>AdjustmentOut</StockTransactionType>
            <StockCode>PROD001</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>-2 stock</Details>
            <Qty>2</Qty>
            <CostPrice>10</CostPrice>
            <SalesPrice xsi:nil="true" />
            <StockTransactionNumber>24</StockTransactionNumber>
            <CustomFields />
        </StockTransaction>
    </StockTransactions>
</Company>
```

### Fail File

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
    <StockTransactions>
        <StockTransaction>
            <Id>9</Id>
            <Errors>
                <Error>
                    <Date>2016-11-03T08:48:37.0994209+00:00</Date>
                    <Name>Validation</Name>
                    <Description>PROD002 does not have enough free stock to complete this transfer</Description>
                </Error>
            </Errors>
            <StockTransactionType>Transfer</StockTransactionType>
            <StockCode>PROD003</StockCode>
            <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
            <Reference>NE6 STOCK</Reference>
            <Details>+1 stock</Details>
            <Qty>1</Qty>
            <CostPrice>10</CostPrice>
            <SalesPrice xsi:nil="true" />
            <StockTransactionNumber xsi:nil="true" />
            <CustomFields />
        </StockTransaction>
    </StockTransactions>
</Company>
```