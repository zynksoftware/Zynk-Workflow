---
slug: sage-200-purchase-invoice-xml
title: Sage 200 Purchase Invoice XML
---
Import Purchase Invoices allows you to create new purchase invoices in Sage 200, potentially completing the related purchase order depending on the data provided.
Sample XML snippets are provided throughout, these are separated out for clarity and so that the hierarchy of the fields relative to the Company XML object model can be easily identified.

## Preventing Duplication of Previously Imported Purchase Invoices
You can optionally provide an Id for each purchase invoice, populating it with the unique identifier of the purchase invoice from the external system (where the data originated). Any successfully imported purchase invoice Id's will be stored in an internal database associated with the Workflow. The Import Purchase Invoices task can then be set to prevent duplicates based on the stored Id's, preventing accidental reprocessing of already imported purchase invoices.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1 | string | 4000 | Optional | The Zynk Id of the Sage 200 purchase invoice. _See paragraph above for details of how this is used._  |

```xml
<?xml version="1.0"?>
<Company>
  <PurchaseInvoices>
    <PurchaseInvoice>
      <Id>1</Id>
    </PurchaseInvoice>
  </PurchaseInvoices>
</Company>
```

## Purchase Order Lookup
In order to lookup the purchase order to invoice, one of the following identifiers can be used, if multiple identifiers are specified then the following precedence is used: -

 * PurchaseOrderUniqueId,
 * PurchaseOrderNumber,
 * PurchaseOrderId,
 * SupplierOrderNumber

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| PurchaseOrderUniqueId | - | 5679 | int | - | Dependant | The database ID of the Sage 200 purchase order. In the Zynk PurchaseOrder object, this would be the UniqueId specified in the success file of a successfully imported PurchaseOrder or in the export file from Sage 200. If this data is obtained via direct SQL access to Sage 200, then this relates to the POPOrderReturn.POPOrderReturnID |
| PurchaseOrderNumber | Order no | 0000000001 | int | - | Dependant | The Order no of the Sage 200 purchase order. In the Zynk PurchaseOrder object, this would be the PurchaseOrderNumber specified in the success file of a successfully imported PurchaseOrder or in the export file from Sage 200. If this data is obtained via direct SQL access to Sage 200, then this relates to the POPOrderReturn.DocumentNo  |
| PurchaseOrderId | - | PO-1234 | string | 4000 | Dependant | The Id of the Zynk PurchaseOrder. If the PurchaseOrder was previously imported by Zynk and an Id (3rd party system identifier) was specified in the XML, then this can be used to match to the Sage 200 PurchaseOrder. This will only be valid in scenarios where the PurchaseOrder was created by Zynk and an Id was specified on the purchase order, this is not something that could be obtained directly via SQL access to Sage 200. |
| SupplierOrderNumber | 	Supplier Reference no | SupplierRef1234 | string | 30 | Dependant | The Supplier reference no of the Sage 200 purchase order. In the Zynk PurchaseOrder object, this would be the SupplierOrderNumber specified in the success file of a successfully imported PurchaseOrder or in the export file from Sage 200. If this data is obtained via direct SQL access to Sage 200, then this relates to the POPOrderReturn.SupplierDocumentNo |

```xml
<?xml version="1.0"?>
<Company>
  <PurchaseInvoices>
    <PurchaseInvoice>
      <PurchaseOrderUniqueId>5679</PurchaseOrderUniqueId>
      <PurchaseOrderNumber>0000000001</PurchaseOrderNumber>
      <PurchaseOrderId>PO-1234</PurchaseOrderId>
      <SupplierOrderNumber>SupplierRef1234</SupplierOrderNumber>
    </PurchaseInvoice>
  </PurchaseInvoices>
</Company>
```

## Purchase Invoice Fields

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| InvoiceNumber | Reference | PI-123 | string | 30 | Optional | If not specified then the created purchase invoice transaction will not have a reference populated, advised to be populated |
| InvoiceDate | Date | 2019-07-11T00:00:00 | date | - | Optional | If not specified then the date that the data is processed will be used for the created purchase invoice transaction |
| InvoiceSecondReference | Second Reference | REF-456 | string | 30 | Optional | - |

```xml
<?xml version="1.0"?>
<Company>
  <PurchaseInvoices>
    <PurchaseInvoice>
      <InvoiceNumber>PI-123</InvoiceNumber>
      <InvoiceDate>2019-07-11T00:00:00</InvoiceDate>
      <InvoiceSecondReference>REF-456</InvoiceSecondReference>
    </PurchaseInvoice>
  </PurchaseInvoices>
</Company>
```

## Receipt Notes
If no ReceiptNotes are provided, then the routine will identify which lines have a received quantity in Sage 200 but do not have a matching invoiced quantiy and invoice these remaining lines so that the total invoiced quantity is equal to the total received quantity.

If goods received notes (GRNs) are provided in the ReceiptNotes collection, the routine will look for these GRNs against the matched Sage 200 Purchase Order, identify the received quantity on these lines and the total invoiced quantity across the lines of the purchase order, and invoice the difference.

Please note that this will mean that the process will never result in an invoiced quantity that is greater than the received quantity, i.e. the process will not allow over invoicing as the quantity to invoice is always determined by the received quantity.

Please note that the process will use the default price that Sage 200 determines, i.e. the unit price of the purchase order line.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| GRNNumber | GRN Number | 0000000011 | int | - | Optional | The GRN No of the Sage 200 purchase order delivery (receipt). Via direct SQL access to Sage 200, then this relates to the POPReceiptReturn.DocumentNo |

```xml
<?xml version="1.0"?>
<Company>
  <PurchaseInvoices>
    <PurchaseInvoice>
      <ReceiptNotes>
        <ReceiptNote>
          <GRNNumber>0000000011</GRNNumber>
        </ReceiptNote>
      </ReceiptNotes>
    </PurchaseInvoice>
  </PurchaseInvoices>
</Company>
```

## XML Sample
```xml
<?xml version="1.0"?>
<Company>
  <PurchaseInvoices>
    <PurchaseInvoice>
      <Id>PurchaseInvoice1234</Id>
      <PurchaseOrderUniqueId>5679</PurchaseOrderUniqueId>
      <PurchaseOrderNumber>0000000001</PurchaseOrderNumber>
      <PurchaseOrderId>PO-1234</PurchaseOrderId>
      <SupplierOrderNumber>SupplierRef1234</SupplierOrderNumber>
      <InvoiceNumber>PI-123</InvoiceNumber>
      <InvoiceDate>2019-07-11T00:00:00</InvoiceDate>
      <InvoiceSecondReference>REF-456</InvoiceSecondReference>
      <ReceiptNotes>
        <ReceiptNote>
          <GRNNumber>0000000011</GRNNumber>
        </ReceiptNote>
      </ReceiptNotes>
    </PurchaseInvoice>
  </PurchaseInvoices>
</Company>
```
