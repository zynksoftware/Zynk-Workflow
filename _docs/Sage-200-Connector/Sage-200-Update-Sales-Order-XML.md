---
slug: sage-200-update-sales-order-xml
title: Sage 200 Update Sales Order XML
---
Update Sales Orders allows you to update header analysis codes on existing orders and returns (sales documents) in Sage 200, and progress the documents through the ordering process (allocate, despatch, receive, amend allocations, amend despatches, amend receipts).   

Sample XML snippets are provided throughout, these are separated out for clarity. A full sample is provided at the bottom of this article.


## Matching Sales Orders/Returns
When updating sales documents in Sage, you must provide one of the following key fields to identify the document to update. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| UniqueId | SOPOrderReturnID | 236991 | int | - | Required, unless using SalesOrderNumber, Id or CustomerOrderNumber | The Sage 200 Sales Order/Return database id (not visible in Sage UI). |
| SalesOrderNumber | Order no/Return no | 0000000024 | string | 20 | Required, unless using UniqueId, Id or CustomerOrderNumber | The Sage 200 document number. |
| Id | - | 123 | string | 4000 | Required, unless using UniqueId, SalesOrderNumber or CustomerOrderNumber | The Zynk Id of the Sage 200 document; assumes that the document was imported in the same Workflow that the Update Sales Orders task is running from. |
| CustomerOrderNumber | Customer order no | 196 | string | 30 | Required, unless using UniqueId, SalesOrderNumber or Id | The Sage 200 customer order number; if more than one document exists with the same customer order no, the first match will be processed. |

You should also specify the document type that you would like to update. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| SalesOrderType | Type | SopInvoice | enum | - | Optional, assumed SopInvoice if not provided | The Sage 200 Sales Order/Return type. **SopInvoice** - Sales Order **SopReturn** - Sales Return |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <!-- Matching Sales Order/Return by UniqueId -->
    <SalesOrder>
      <UniqueId>236991</UniqueId>
      <SalesOrderType>SopInvoice</SalesOrderType>
    </SalesOrder>   

    <!-- Matching Sales Order/Return by SalesOrderNumber --> 
    <SalesOrder>
      <SalesOrderNumber>0000000024</SalesOrderNumber>
      <SalesOrderType>SopInvoice</SalesOrderType>
    </SalesOrder>    

    <!-- Matching Sales Order/Return by Id --> 
    <SalesOrder>
      <Id>123</Id>
      <SalesOrderType>SopInvoice</SalesOrderType>
    </SalesOrder>    

    <!-- Matching Sales Order/Return by CustomerOrderNumber --> 
    <SalesOrder>
      <CustomerOrderNumber>276</CustomerOrderNumber>
      <SalesOrderType>SopReturn</SalesOrderType>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Analysis codes
Analysis codes are imported from a collection, so you can import as many as are setup within Sage 200.  We lookup analysis codes by matching the Name from our XML to the Field Label in Sage.  The values that can be imported depend on how the analysis code is configured, if you need to import any value ensure Enter Free Text is enabled from Accounting System Manager -> Settings -> Maintain Analysis Codes. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Name | Analysis Code | Customer Type | string | 60 | Required | The analysis code must already exist in Sage 200. |
| Value | Value | A | string | 60 | Optional | The value must already exist, unless Enter Free Text is enabled. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Customer Type</Name>
          <Value>A</Value>
        </AnalysisCode>
        <AnalysisCode>
          <Name>Order Source</Name>
          <Value>Web</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Order Priority
You can update the order priority field by providing the XML below. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Priority | Order Priority | A | string | 1 | Optional | The order priority should be a single letter from A-Z. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <Priority>A</Priority>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Adjusting Sales Order/Return Items
When adjusting sales document item lines in Sage (allocating, amending allocations, despatching, amending despatches, receiving, and amending receipts), you must provide one of the following fields to match the item line that you would like to process.   

_Every Sales Order/Return is processed in it's entirety, meaning that if any of the Item adjustments cannot be fulfilled then all adjustments will be undone, you can think of each SalesOrder element provided in the data as representing a transaction against Sage, which will be rolled back if any of the item adjustments are unsuccessful. (Any rolled back operations will be captured against the Sage 200 Stock Item History)_

If you want any valid Item adjustments to be processed regardless of whether or not other Item adjustments on the Order/Return are processed (atomically) then you should provide each Item adjustment in a separate SalesOrder element in the data. See examples at the bottom of this document.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| UniqueId | SOPOrderReturnLineID | 233748 | int | - | Required, unless using Sku | The Sage 200 Sales Order/Return line database id (not visible in Sage UI). |
| Sku | Item | TILE/WHT/20X20 | string | 30 | Required, unless using UniqueId | The Sage 200 item code. |
| PrintSequenceNumber | - | 2 | int | - | Optional, if using Sku | The position of the item on the Sage 200 document, could be used if adjusting a particular sku that appears more than once or for stricter validation. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <!-- Matching Sales Order/Return Item by UniqueId -->
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <UniqueId>236991</UniqueId>
        </Item>
      </SalesOrderItems>
    </SalesOrder>    
    
    <!-- Matching Sales Order/Return Item by Sku -->
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <PrintSequenceNumber>2</PrintSequenceNumber>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Allocating Sales Order Items
To allocate a sales order item, you must specify the amount to allocate.   

_N.B. It is not valid to provide a QtyToAmendAllocate on the same XML Item that QtyToAllocate has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToAllocate | Qty Allocated | 1 | decimal | - | Required | The quantity to allocate. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <QtyToAllocate>2</QtyToAllocate>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Amending Sales Order Item Allocations
To amend the allocation of a sales order item, you must specify the amount to amend the allocation by. 

_N.B. It is not valid to provide a QtyToAllocate on the same XML Item that QtyToAmendAllocate has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToAmendAllocate | Qty Allocated | 1 | decimal | - | Required | The quantity to reduce the allocation by. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <QtyToAmendAllocate>2</QtyToAmendAllocate>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Despatching Sales Order Items
To despatch a sales order item, you must specify the amount to despatch.   

_N.B. It is not valid to provide a QtyToAmendDespatch on the same XML Item that QtyToDespatch has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToDespatch | Qty to Despatch | 5 | decimal | - | Required | The quantity to despatch. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <QtyToDespatch>5</QtyToDespatch>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Amending Sales Order Item Despatches
To amend the despatch of a sales order item, you must specify the amount to amend the despatch by. 

_N.B. It is not valid to provide a QtyToDespatch on the same XML Item that QtyToAmendDespatch has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToAmendDespatch | Amended Despatch Qty | 2 | decimal | - | Required | The quantity to reduce the despatch by. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <QtyToAmendDespatch>2</QtyToAmendDespatch>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Receiving Sales Return Items
To receive a sales return item, you must specify the amount to receive. 

_N.B. It is not valid to provide a QtyToAmendReceive on the same XML Item that QtyToReceive has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToReceive | Qty to Return | 1 | decimal | - | Required | The quantity to receive. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <QtyToReceive>1</QtyToReceive>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Amending Sales Return Item Receipts
To amend the receipt of a sales return item, you must specify the amount to amend the receipt by. 

_N.B. It is not valid to provide a QtyToReceive on the same XML Item that QtyToAmendReceive has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToAmendReceive | Amended Receipt Qty | 2 | decimal | - | Required | The quantity to reduce the receipt by. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <QtyToAmendReceive>2</QtyToAmendReceive>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Adjusting Traceable Items
If you deal with traceable (batch or serial) items in Sage 200, then you can optionally provide the traceable identification numbers to receive the goods as. 

### Batch Items
If the item line being processed on the goods received note is configured in Sage 200 as a batch item, you can specify the batch information on the goods received note according to the below mapping. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| IdentificationNo | Batch No | 0000000001 | string | 30 | Required | The identifier of the traceable batch to process. |
| Quantity | Qty Allocated/Qty to Despatch/Qty To Return | 2 | decimal | - | Required | The quantity of the traceable batch to use on the adjustment. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Batches>
            <Batch>
              <IdentificationNo>0000000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Serial Items
If the item line being processed on the goods received note is configured in Sage 200 as a serial item, you can specify the batch information on the goods received note according to the below mapping. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| IdentificationNo | Batch No | 0000000001 | string | 30 | Required | The identifier of the serial item to process. |
| Quantity | Qty Allocated/Qty to Despatch/Qty To Return | 1 | decimal | - | Required | The quantity of a serial adjustment should always be 1. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Batches>
            <Batch>
              <IdentificationNo>0000000001</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Full Samples
### Updating Sales Order
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderNumber>0000000024</SalesOrderNumber>
      <SalesOrderType>SopInvoice</SalesOrderType>
      <SalesOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToAllocate>2</QtyToAllocate>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToDespatch>2</QtyToDespatch>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
        <Item>
          <Sku>TILE/BLK/20X20</Sku>
          <QtyToAmendDespatch>2</QtyToAmendDespatch>
          <Batches>
            <Batch>
              <IdentificationNo>SER0000001</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
            <Batch>
              <IdentificationNo>SER0000002</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
          </Batches>
        </Item>
        <Item>
          <Sku>TILE/BLK/20X20</Sku>
          <QtyToAmendAllocate>2</QtyToAmendAllocate>
          <Batches>
            <Batch>
              <IdentificationNo>SER0000001</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
            <Batch>
              <IdentificationNo>SER0000002</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Customer Type</Name>
          <Value>A</Value>
        </AnalysisCode>
        <AnalysisCode>
          <Name>Order Source</Name>
          <Value>Web</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Updating Sales Return
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <CustomerOrderNumber>WEBORDER-1234</CustomerOrderNumber>
      <SalesOrderType>SopReturn</SalesOrderType>
      <SalesOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToReceive>2</QtyToReceive>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000004</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToAmendReceive>2</QtyToAmendReceive>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000040</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Retail</Name>
          <Value>Yes</Value>
        </AnalysisCode>
        <AnalysisCode>
          <Name>Order Source</Name>
          <Value>Web</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Updating Sales Order Items Atomically
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderNumber>0000000025</SalesOrderNumber>
      <SalesOrderType>SopInvoice</SalesOrderType>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Customer Type</Name>
          <Value>A</Value>
        </AnalysisCode>
        <AnalysisCode>
          <Name>Order Source</Name>
          <Value>Web</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </SalesOrder>
    <SalesOrder>
      <SalesOrderNumber>0000000025</SalesOrderNumber>
      <SalesOrderType>SopInvoice</SalesOrderType>
      <SalesOrderItems>
        <Item>
          <Sku>TILE/WHT/20X24</Sku>
          <QtyToAllocate>2</QtyToAllocate>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000010</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
    <SalesOrder>
      <SalesOrderNumber>0000000025</SalesOrderNumber>
      <SalesOrderType>SopInvoice</SalesOrderType>
      <SalesOrderItems>
        <Item>
          <Sku>TILE/WHT/20X22</Sku>
          <QtyToDespatch>2</QtyToDespatch>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000020</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
    <SalesOrder>
      <SalesOrderNumber>0000000025</SalesOrderNumber>
      <SalesOrderType>SopInvoice</SalesOrderType>
      <SalesOrderItems>
        <Item>
          <Sku>TILE/BLK/20X21</Sku>
          <QtyToAmendDespatch>2</QtyToAmendDespatch>
          <Batches>
            <Batch>
              <IdentificationNo>SER0000100</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
            <Batch>
              <IdentificationNo>SER0000200</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
    <SalesOrder>
      <SalesOrderNumber>0000000025</SalesOrderNumber>
      <SalesOrderType>SopInvoice</SalesOrderType>
      <SalesOrderItems>
        <Item>
          <Sku>TILE/BLK/20X20</Sku>
          <QtyToAmendAllocate>2</QtyToAmendAllocate>
          <Batches>
            <Batch>
              <IdentificationNo>SER0000150</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
            <Batch>
              <IdentificationNo>SER0000250</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
          </Batches>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```