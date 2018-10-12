---
slug: importing-invoice-payments-via-connectwise-rest-interface
title: Importing Invoice Payments via ConnectWise REST Interface
---
This task will import invoice payments into ConnectWise from an XML file. See below for a sample input file. 

Invoice payments are created/updated based on the following rules:
* If an `<id>` is specified, the task will update the payment with this ID.
* If an `<externalId>` is specified, and a corresponding entry is found in Zynk's truth table, the task will update the payment with this ID.
* If a payment already exists for the specified invoice, the task will update the existing payment.
* If none of the above conditions are met, the task will create a new payment.

When updating existing payments, only writeable fields specified in the input file will be updated. Any other fields will keep their existing values.

Please note that ConnectWise only allow a single payment per invoice.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the file to output any invoice payments that failed to import. The error messages will be included in the file.

### Input File
_Required_  
The name of the file containing the invoice payments to upload to ConnectWise. A sample file is provided below.

### Success File
_Required_  
The name of the file to output any successfully imported invoice payments to.

### Prevent Reprocessing
_Required_  
Set this option to 'True' to prevent the same invoice payment being processed more than once by Zynk. An `<externalId>` must be provided in the input file for this to work.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<InvoicePayments xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <InvoicePayment>
    <id>2</id>
    <externalId>1234</externalId>
    <invoice>
      <id>206</id>
    </invoice>
    <amount>10</amount>
    <paymentDate>2018-10-11T00:00:00Z</paymentDate>
  </InvoicePayment>
</InvoicePayments>
```
