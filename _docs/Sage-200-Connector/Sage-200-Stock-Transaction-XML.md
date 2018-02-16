---
slug: sage-200-stock-transaction-xml
title: Sage 200 Stock Transaction XML
---
Import Stock Transactions allows you to create new stock transactions in Sage 200, optionally creating any associated history and nominal postings automatically.
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
| StockTransactionType | Movement Type | MovementIn | enum | - | Required | The type of stock transaction to create in Sage 200. _See the below for a list of the available Zynk stock transaction types and the Sage 200 stock transactions that they relate to._ |

### MovementIn / In - Unknown Source
Equivalent of using the 'Add Stock' button via the Sage 200 UI.
_You should only ever use this transaction type if you are importing financial transaction information against the Purchase Ledger directly, rather than importing Purchase Orders, but still require the stock quantities to be adjusted appropriately._

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>MovementIn</StockTransactionType>
          </StockTransaction>
     </StockTransactions>
</Company>
```

### WriteOff / Out - Write Off
Equivalent of using the 'Write Off' button via the Sage 200 UI.

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>WriteOff</StockTransactionType>
          </StockTransaction>
     </StockTransactions>
</Company>
```

### Transfer / Out - Transfer and In - Transfer
Equivalent of using the 'Add Stock' button via the Sage 200 UI.

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>Transfer</StockTransactionType>
          </StockTransaction>
     </StockTransactions>
</Company>
```

### GoodsOut / Out - SOP
No equivalent via the Sage 200 UI. This represents Goods being shipped out to a Customer. 
_You should only ever use this transaction type if you are importing financial transaction information against the Sales Ledger directly, rather than importing Sales Orders, but still require the stock quantities to be adjusted appropriately._

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>GoodsOut</StockTransactionType>
          </StockTransaction>
     </StockTransactions>
</Company>
```

## Stock Transaction Fields
The fields in the table below are shared across all stock transaction types.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| StockCode | Code | BOARD001 | string | 30 | Required | The Code of the Stock Item in Sage that you would like to create the stock transaction against. |
| Qty | Quantity | 2 | double | 15, 5 | Required | The amount of stock to adjust in Sage. |
| Reference | Reference | NE6 STOCK | string | 20 | Optional | An optional reference that can be used to help make the stock transaction in Sage easier to identify. |
| SecondReference | Second ref | ORDER55768 | string | 20 | Optional | An optional reference that can be used to help make the stock transaction in Sage easier to identify. |
| StockTransactionDate | Date | 2016-05-04T00:00:00 | datetime | - | Optional | The date of the stock transaction. Defaults to the date the transaction is imported if not provided. _The date needs to be in XSD format (yyyy-MM-ddTHH:mm:ss), only the date is displayed via the Sage UI._ |
| Details | Description | +2 stock | string | - | Optional | An additional description that can be provided |
| AnalysisCode1 | Analysis code 1 | Website Sales Stock | string | 60 | Optional | An optional analysis code that be used for storing additional information against the stock transaction in Sage. |
| AnalysisCode2 | Analysis code 2 | Back To Back | string | 60 | Optional | An optional analysis code that be used for storing additional information against the stock transaction in Sage. |
| AnalysisCode3 | Analysis code 3 | Automatic | string | 60 | Optional | An optional analysis code that be used for storing additional information against the stock transaction in Sage. |

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockCode>BOARD001</StockCode>
               <Qty>2</Qty>
               <Reference>NE6 STOCK</Reference>
               <SecondReference>ORDER55768</SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>+2 stock</Details>
               <AnalysisCode1>Website Sales Stock</AnalysisCode1>
               <AnalysisCode2>Back To Back</AnalysisCode2>
               <AnalysisCode3>Automatic</AnalysisCode3>
          </StockTransaction>
     </StockTransactions>
</Company>
```

## Providing Traceable Information for a Stock Transactions
If you deal with traceable (batch or serial) stock items in Sage 200, you can optionally provide the traceable identification numbers that the stock transactions relate to.  

_Please note that the traceable configuration settings against the stock item in Sage 200 determines if you need to provide traceable information when importing the stock transactions. You should check the Batch/Serial Nos tab on the stock item in Sage to confirm when traceable information needs to be provided._

### Batch Items
If the stock item on the stock transaction is configured in Sage 200 as a batch item, then you can specify the batch information associated with the stock transaction according to the below mapping. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| IdentificationNo | Batch No | BATCH00001 | string | 30 | Required | The identifier of the traceable batch to process. |
| Quantity | Quantity | 2 | decimal | 15, 5 | Required | The quantity of the traceable batch to use on the adjustment. |

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Batches>
                    <Batch>
                         <IdentificationNo>BATCH00001</IdentificationNo>
                         <Quantity>2</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

### Serial Items
If the stock item on the stock transaction is configured in Sage 200 as a serial item, you can specify the serial information associated with the stock transaction according to the below mapping. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| IdentificationNo | Serial No | SERIAL0001 | string | 30 | Required | The identifier of the serial item to process. |
| Quantity | - | 1 | decimal | - | Required | The quantity of a serial adjustment should always be 1. |

```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Batches>
                    <Batch>
                         <IdentificationNo>SERIAL0001</IdentificationNo>
                         <Quantity>1</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

## MovementIn Transaction Fields
The following additional fields can be provided when importing a MovementIn transaction.

_See the **Stock Transaction Fields** and the **Providing Traceable Information for a Stock Transaction** areas above for the other fields that can be set on this type of stock transaction._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| CostPrice | Unit cost price | 12.5 | decimal | 18, 5 | Optional | The unit cost price for the purchased stock. |
| Location | Warehouse | HOME | string | 20 | Required | The name of the warehouse to add the stock to. |
| Bin | Bin | Unspecified | string | 20 | Optional | The name of the bin to add the stock to.
Will default to the first returned by Sage. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <CostPrice>12.5</CostPrice>  
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>
          </StockTransaction>
     </StockTransactions>
</Company>
```

### Providing Traceable Batch Attributes When Processing MovementIn (Add Stock) Transactions
If you deal with traceable (batch or serial) items in Sage 200, it is possible that the stock item is configured to use 'Sell by dates', 'Use by dates', 'Alternative Refs' and/or other custom batch attributes configured at the product group level. You can optionally specify batch attributes when importing MovementIn transactions.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Name | Title | Finish | string | 60 | Required | The name of the attribute to set (should be provided as it appears within Sage). To specify 'Alternative Ref', 'Sell By' or 'Use By', use. _AlternativeReference_ or _UseByDate_ or _SellByDate_ |
| Value | Value | Glossy | string | 60 | Optional | The value to use for the attribute on the batch. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Batches>
                    <Batch>
                         <Attributes>
                              <!-- If specifying Alternative Reference-->
                              <Attribute>
                                   <Name>AlternativeReference</Name>
                                   <Value>ORANGE_00001_00004</Value>
                              </Attribute>
                              <!-- If specifying Use by or Sell by date-->
                              <Attribute>
                                   <Name>UseByDate</Name>
                                   <!-- The following date format should be used -->
                                   <Value>2016-05-04</Value>
                              </Attribute>
                              <Attribute>
                                   <Name>SellByDate</Name>
                                   <!-- The following date format should be used -->
                                   <Value>2016-05-04</Value>
                              </Attribute>
                              <!-- If specifying custom attributes-->
                              <Attribute>
                                   <!-- The title should match the title in Sage exactly -->
                                   <Name>Finish</Name>
                                   <Value>Glossy</Value>
                              </Attribute>
                         </Attributes>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

## WriteOff Transaction Fields
The following additional fields can be provided when importing a WriteOff transaction.

_See the **Stock Transaction Fields** and the **Providing Traceable Information for a Stock Transaction** areas above for the other fields that can be set on this type of stock transaction._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| ReasonCode | Write off category | DAMAGED | string | 20 | Required | The name of the Write off category to use. |
| Location | Warehouse | HOME | string | 20 | Required | The name of the warehouse to write off stock from. |
| Bin | Bin | Unspecified | string | 20 | Optional | The name of the bin to write off stock from.
Will default to the first returned by Sage. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <ReasonCode>DAMAGED</ReasonCode>  
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>
          </StockTransaction>
     </StockTransactions>
</Company>
```

## Transfer Transaction Fields
The following additional fields can be provided when importing a Transfer transaction.

_See the **Stock Transaction Fields** and the **Providing Traceable Information for a Stock Transaction** areas above for the other fields that can be set on this type of stock transaction._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| TransferFrom/Warehouse | Stock Location/Warehouse | HOME | string | 20 | Required | The name of the warehouse to move the stock from. |
| TransferFrom/Bin | Stock Location/Bin | Unspecified | string | 20 | Optional | The name of the bin to move the stock from. |
| TransferTo/Warehouse | Transferred To/Warehouse | FACTORY | string | 20 | Required | The name of the warehouse to move the stock to. |
| TransferTo/Bin | Transferred To/Bin | Unspecified | string | 20 | Optional | The name of the bin to move the stock to. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <TransferFrom>
                    <Location>HOME</Location>
                    <Bin>Unspecified</Bin>
               </TransferFrom>  
               <TransferTo>
                    <Location>FACTORY</Location>
                    <Bin>Unspecified</Bin>
               </TransferTo>  
          </StockTransaction>
     </StockTransactions>
</Company>
```


## GoodsOut Transaction Fields
The following additional fields can be provided when importing a GoodsOut transaction.

_See the **Stock Transaction Fields** and the **Providing Traceable Information for a Stock Transaction** areas above for the other fields that can be set on this type of stock transaction._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| SourceAreaReference | Code | ABB001 | string | 8 | Required | The sales ledger (customer) account number that the goods out transaction is for. |
| SalesPrice | Unit sales price | 25.75 | double | 18, 5 | Required | The unit price the goods were sold at. |
| CostPrice | Unit cost price | 12.5 | double | 18, 5 | Optional | The unit price the goods were bought at. _Can only be set for stock items set up in Sage to use the Standard Cost Method._ |
| Location | Warehouse | HOME | string | 20 | Required | The name of the warehouse to ship stock from. |
| Bin | Bin | Unspecified | string | 20 | Optional | The name of the bin to ship stock from.
Will default to the first returned by Sage. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <SourceAreaReference>ABB001</SourceAreaReference>  
               <SalesPrice>25.75</SalesPrice>
               <CostPrice>12.5</CostPrice>
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>
          </StockTransaction>
     </StockTransactions>
</Company>
```

## XML Samples
### MovementIn
#### Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>MovementIn</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>2</Qty> 
               <Location>HOME</Location>
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>1</Id>
               <StockTransactionType>MovementIn</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>2</Qty>
               <Reference>NE6 STOCK</Reference>
               <SecondReference>ORDER55768</SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>+2 stock</Details>
               <AnalysisCode1>Website Sales Stock</AnalysisCode1>
               <AnalysisCode2>Back To Back</AnalysisCode2>
               <AnalysisCode3>Automatic</AnalysisCode3>
               <CostPrice>12.5</CostPrice>  
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>MovementIn</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>2</Qty> 
               <Location>HOME</Location>
               <Batches>
                    <Batch>
                         <IdentificationNo>BATCH00001</IdentificationNo>
                         <Quantity>2</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>2</Id>
               <StockTransactionType>MovementIn</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>2</Qty>
               <Reference>NE6 STOCK</Reference>
               <SecondReference>ORDER55768</SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>+2 stock</Details>
               <AnalysisCode1>Website Sales Stock</AnalysisCode1>
               <AnalysisCode2>Back To Back</AnalysisCode2>
               <AnalysisCode3>Automatic</AnalysisCode3>
               <CostPrice>12.5</CostPrice>  
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>
               <Batches>
                    <Batch>
                         <IdentificationNo>BATCH00001</IdentificationNo>
                         <Quantity>2</Quantity>
                         <Attributes>
                              <Attribute>
                                   <Name>AlternativeReference</Name>
                                   <Value>ORANGE_00001_00004</Value>
                              </Attribute>
                              <Attribute>
                                   <Name>UseByDate</Name>
                                   <Value>2016-05-04</Value>
                              </Attribute>
                              <Attribute>
                                   <Name>SellByDate</Name>
                                   <Value>2016-05-04</Value>
                              </Attribute>
                              <Attribute>
                                   <Name>Finish</Name>
                                   <Value>Glossy</Value>
                              </Attribute>
                         </Attributes>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

### WriteOff
#### Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>WriteOff</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <ReasonCode>DAMAGED</ReasonCode>
               <Location>HOME</Location>
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>3</Id>
               <StockTransactionType>WriteOff</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <Reference>DAMAGED</Reference>
               <SecondReference>ORDER55769</SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>damaged during delivery</Details>
               <AnalysisCode1></AnalysisCode1>
               <AnalysisCode2></AnalysisCode2>
               <AnalysisCode3></AnalysisCode3>
               <ReasonCode>DAMAGED</ReasonCode>
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>    
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>WriteOff</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <ReasonCode>DAMAGED</ReasonCode>
               <Location>HOME</Location>
               <Batches>
                    <Batch>
                         <IdentificationNo>SERIAL0001</IdentificationNo>
                         <Quantity>1</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>3</Id>
               <StockTransactionType>WriteOff</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <Reference>DAMAGED</Reference>
               <SecondReference>ORDER55769</SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>damaged during delivery</Details>
               <AnalysisCode1></AnalysisCode1>
               <AnalysisCode2></AnalysisCode2>
               <AnalysisCode3></AnalysisCode3>
               <ReasonCode>DAMAGED</ReasonCode>
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>
               <Batches>
                    <Batch>
                         <IdentificationNo>SERIAL0001</IdentificationNo>
                         <Quantity>1</Quantity>
                    </Batch>
               </Batches>   
          </StockTransaction>
     </StockTransactions>
</Company>
```

### Transfer
#### Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>Transfer</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <TransferFrom>
                    <Location>HOME</Location>
               </TransferFrom>  
               <TransferTo>
                    <Location>FACTORY</Location>
               </TransferTo>                             
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>5</Id>
               <StockTransactionType>Transfer</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <Reference>Backup Stock</Reference>
               <SecondReference></SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>Moving stock from home to factory</Details>
               <AnalysisCode1></AnalysisCode1>
               <AnalysisCode2></AnalysisCode2>
               <AnalysisCode3></AnalysisCode3>
               <TransferFrom>
                    <Location>HOME</Location>
                    <Bin>Unspecified</Bin>
               </TransferFrom>  
               <TransferTo>
                    <Location>FACTORY</Location>
                    <Bin>Unspecified</Bin>
               </TransferTo>                             
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>Transfer</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <TransferFrom>
                    <Location>HOME</Location>
               </TransferFrom>  
               <TransferTo>
                    <Location>FACTORY</Location>
               </TransferTo>
               <Batches>
                    <Batch>
                         <IdentificationNo>SERIAL0001</IdentificationNo>
                         <Quantity>1</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>5</Id>
               <StockTransactionType>Transfer</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>1</Qty>
               <Reference>Backup Stock</Reference>
               <SecondReference></SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>Moving stock from home to factory</Details>
               <AnalysisCode1></AnalysisCode1>
               <AnalysisCode2></AnalysisCode2>
               <AnalysisCode3></AnalysisCode3>
               <TransferFrom>
                    <Location>HOME</Location>
                    <Bin>Unspecified</Bin>
               </TransferFrom>  
               <TransferTo>
                    <Location>FACTORY</Location>
                    <Bin>Unspecified</Bin>
               </TransferTo>            
               <Batches>
                    <Batch>
                         <IdentificationNo>SERIAL0001</IdentificationNo>
                         <Quantity>1</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

### GoodsOut
#### Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>GoodsOut</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>4</Qty>
               <SourceAreaReference>ABB001</SourceAreaReference>
               <SalesPrice>25.75</SalesPrice>
               <Location>HOME</Location>
          </StockTransaction>
     </StockTransactions>
</Company>
```
#### Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>7</Id>
               <StockTransactionType>GoodsOut</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>4</Qty>
               <Reference>ORDER55667</Reference>
               <SecondReference></SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>First shipment to customer</Details>
               <AnalysisCode1></AnalysisCode1>
               <AnalysisCode2></AnalysisCode2>
               <AnalysisCode3></AnalysisCode3>
               <SourceAreaReference>ABB001</SourceAreaReference>
               <SalesPrice>25.75</SalesPrice>
               <CostPrice>12.5</CostPrice>
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>           
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Minimal Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <StockTransactionType>GoodsOut</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>4</Qty>
               <SourceAreaReference>ABB001</SourceAreaReference>
               <SalesPrice>25.75</SalesPrice>
               <Location>HOME</Location>
               <Batches>
                    <Batch>
                         <IdentificationNo>SERIAL0001</IdentificationNo>
                         <Quantity>1</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```

#### Traceable Full Information
```xml
<?xml version="1.0"?>
<Company>
     <StockTransactions>
          <StockTransaction>
               <Id>7</Id>
               <StockTransactionType>GoodsOut</StockTransactionType>
               <StockCode>BOARD001</StockCode>
               <Qty>4</Qty>
               <Reference>ORDER55667</Reference>
               <SecondReference></SecondReference>
               <StockTransactionDate>2016-05-04T00:00:00</StockTransactionDate>
               <Details>First shipment to customer</Details>
               <AnalysisCode1></AnalysisCode1>
               <AnalysisCode2></AnalysisCode2>
               <AnalysisCode3></AnalysisCode3>
               <SourceAreaReference>ABB001</SourceAreaReference>
               <SalesPrice>25.75</SalesPrice>
               <CostPrice>12.5</CostPrice>
               <Location>HOME</Location>
               <Bin>Unspecified</Bin>
               <Batches>
                    <Batch>
                         <IdentificationNo>SERIAL0001</IdentificationNo>
                         <Quantity>1</Quantity>
                    </Batch>
               </Batches>
          </StockTransaction>
     </StockTransactions>
</Company>
```