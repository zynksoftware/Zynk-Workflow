---
slug: importing-purchase-invoices-into-sage-200
title: Importing Purchase Invoices into Sage 200
---
This task will import new purchase invoice records in Zynk XML format into Sage 200.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed records in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported records in Zynk XML format.

### Prevent Duplicates
_Required_  
Set to 'True' to check whether the Id supplied in the  input XML file has already been imported, and if so skip the record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a purchase invoice is shown below. See our [Sage 200 Purchase Invoice XML](sage-200-purchase-invoice-xml) for more details on the Zynk XML Purchase Invoice format for Sage 200.

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