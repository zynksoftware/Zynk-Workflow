---
slug: sage-200-update-purchase-order-xml
title: Sage 200 Update Purchase Order XML
---
The Update Purchase Orders task allows you progress purchase documents in Sage 200 through the ordering process (receiving, amending receipts, returning and amending returns).  

Sample XML snippets are provided throughout, these are separated out for clarity. A full sample is provided at the bottom of this article.

## Matching Purchase Orders/Returns
When updating purchase documents in Sage, you must provide one of the following key fields to identify the document to update. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| UniqueId | POPOrderReturnID | 236991 | int | - | Required, unless using PurchaseOrderNumber, Id or SupplierOrderNumber | The Sage 200 Purchase Order/Return database id (not visible in Sage UI). |
| PurchaseOrderNumber | Order no/Return no | 0000000024 | string | 20 | Required, unless using UniqueId, Id or SupplierOrderNumber | The Sage 200 document number. |
| Id | - | 123 | string | 4000 | Required, unless using UniqueId, PurchaseOrderNumber or SupplierOrderNumber | The Zynk Id of the Sage 200 document; assumes that the document was imported in the same Workflow that the Update Purchase Orders task is running from. |
| SupplierOrderNumber | Supplier reference no | 196 | string | 30 | Required, unless using UniqueId, PurchaseOrderNumber or Id | The Sage 200 supplier reference no; if more than one document exists with the same supplier reference no, the first match will be processed. |

You should also specify the document type that you would like to update. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| PurchaseOrderType | Type | PopInvoice | enum | - | Optional, assumed PopInvoice if not provided | The Sage 200 Purchase Order/Return type. **PopInvoice** - Purchase Order **PopReturn** - Purchase Return |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <!-- Matching Purchase Order/Return by UniqueId-->
    <PurchaseOrder>
      <UniqueId>236991</UniqueId>
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
    </PurchaseOrder>

    <!-- Matching Purchase Order/Return by Id -->
    <PurchaseOrder>
      <Id>123</Id>
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
    </PurchaseOrder>

    <!-- Matching Purchase Order/Return by PurchaseOrderNumber -->   
    <PurchaseOrder>
      <PurchaseOrderNumber>0000000024</PurchaseOrderNumber>
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
    </PurchaseOrder>

    <!-- Matching Purchase Order/Return by SupplierOrderNumber -->    
    <PurchaseOrder>
      <SupplierOrderNumber>196</SupplierOrderNumber>
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Adjusting Purchase Order/Return Items
When adjusting purchase document item lines in Sage (receiving, amending receipts, returning and amending returns), you must provide one of the following fields to match the item line that you would like to process.   

_Every Purchase Order/Return is processed in it's entirety, meaning that if any of the Item adjustments cannot be fulfilled then all adjustments will be undone, you can think of each PurchaseOrder element provided in the data as representing a transaction against Sage, which will be rolled back if any of the item adjustments are unsuccessful. (Any rolled back operations will be captured against the Sage 200 Stock Item History)_

If you want any valid Item adjustments to be processed regardless of whether or not other Item adjustments on the Order/Return are processed (atomically) then you should provide each Item adjustment in a separate PurchaseOrder element in the data. See examples at the bottom of this document.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| UniqueId | POPOrderReturnLineID | 233748 | int | - | Required, unless using Sku | The Sage 200 Purchase Order/Return line database id (not visible in Sage UI). |
| Sku | Item | TILE/WHT/20X20 | string | 30 | Required, unless using UniqueId | The Sage 200 item code. |
| PrintSequenceNumber | - | 2 | int | - | Optional, if using Sku | The position of the item on the Sage 200 document, could be used if adjusting a particular sku that appears more than once or for stricter validation. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <!-- Matching Purchase Order/Return Item by UniqueId -->
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <UniqueId>236991</UniqueId>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>    
    
    <!-- Matching Purchase Order/Return Item by Sku -->
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <PrintSequenceNumber>2</PrintSequenceNumber>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Receiving Purchase Order Items
To receive a purchase order item, you must specify the amount to receive. 

_N.B. It is not valid to provide a QtyToAmendReceive on the same XML Item that QtyToReceive has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToReceive | Qty Received | 1 | decimal | - | Required | The quantity to receive. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseItems>
        <Item>
          <QtyToReceive>1</QtyToReceive>
        </Item>
      </PurchaseItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Amending Purchase Order Items Received
To amend the receipt of a purchase order item, you must specify the amount to amend the receipt by. 

_N.B. It is not valid to provide a QtyToReceive on the same XML Item that QtyToAmendReceive has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToAmendReceive | Qty Received | 1 | decimal | - | Required | The quantity to reduce the receipt by. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <QtyToAmendReceive>2</QtyToAmendReceive>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Returning Purchase Order Items
To return a purchase order item, you must specify the amount to return. 

_N.B. It is not valid to provide a QtyToAmendReturn on the same XML Item that QtyToReturn has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToReturn | Qty Returned | 1 | decimal | - | Required | The quantity to return. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseItems>
        <Item>
          <QtyToReturn>1</QtyToReturn>
        </Item>
      </PurchaseItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Amending Purchase Order Items Returned
To amend the returns of a purchase order item, you must specify the amount to amend the returns by. 

_N.B. It is not valid to provide a QtyToReturn on the same XML Item that QtyToAmendReturn has been provided on._

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| QtyToAmendReturn | Qty Returned | 1 | decimal | - | Required | The quantity to reduce the returns by. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <QtyToAmendReturn>1</QtyToAmendReturn>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Adjusting Traceable Items
If you deal with traceable (batch or serial) items in Sage 200, then you can optionally provide the traceable identification numbers to receive/return the goods as. 

### Batch Items
If the item line being processed on the goods received note is configured in Sage 200 as a batch item, you can specify the batch information on the goods received note according to the below mapping. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| IdentificationNo | Batch No | 0000000001 | string | 30 | Required | The identifier of the traceable batch to process. |
| Quantity | Qty Received/Qty To Return | 2 | decimal | - | Required | The quantity of the traceable batch to use on the adjustment. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToReceive>2</QtyToReceive>
          <Batches>
            <Batch>
              <IdentificationNo>0000000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Serial Items
If the item line being processed on the goods received note is configured in Sage 200 as a serial item, you can specify the batch information on the goods received note according to the below mapping. 

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| IdentificationNo | Batch No | 0000000001 | string | 30 | Required | The identifier of the serial item to process. |
| Quantity | Qty Received/Qty To Return | 1 | decimal | - | Required | The quantity of a serial adjustment should always be 1. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToReceive>2</QtyToReceive>
          <Batches>
            <Batch>
              <IdentificationNo>0000000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Complete Examples
Full samples of the XML are provided below.

### Updating Purchase Order
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderNumber>0000000024</PurchaseOrderNumber>
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
      <PurchaseOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToReceive>2</QtyToReceive>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
        <Item>
          <Sku>TILE/BLK/20X20</Sku>
          <QtyToAmendReceive>2</QtyToAmendReceive>
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
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Updating Purchase Return
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderNumber>0000000025</PurchaseOrderNumber>
      <PurchaseOrderType>PopReturn</PurchaseOrderType>
      <PurchaseOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToReturn>2</QtyToReturn>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
        <Item>
          <Sku>TILE/BLK/20X20</Sku>
          <QtyToAmendReturn>2</QtyToAmendReturn>
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
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Updating Purchase Order Atomically
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderNumber>0000000024</PurchaseOrderNumber>
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
      <PurchaseOrderItems>
        <Item>
          <Sku>TILE/WHT/20X20</Sku>
          <QtyToReceive>2</QtyToReceive>
          <Batches>
            <Batch>
              <IdentificationNo>BAT0000001</IdentificationNo>
              <Quantity>2</Quantity>
            </Batch>
          </Batches>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
    <PurchaseOrder>
      <PurchaseOrderNumber>0000000024</PurchaseOrderNumber>
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
        <Item>
          <Sku>TILE/BLK/20X20</Sku>
          <QtyToAmendReceive>2</QtyToAmendReceive>
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
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```
