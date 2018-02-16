---
slug: updating-invoice-payments-to-connectwise-accounting-interface
redirect_from: "/article/956-updating-invoice-payments-to-connectwise-accounting-interface"
title: Updating Invoice Payments to ConnectWise Accounting Interface
---


This task will update the payment information associated with ConnectWise invoices. The Input that you provide must match the XML schema in the examples below. This task is typically used for integrations with accounting systems, normally where the process involves sending invoices from ConnectWise but reconciling payments in the accounting system, this task can then be used to automatically capture payments taken in the accounting system against the appropriate ConnectWise invoices.



Only a single payment per ConnectWise invoice can be set via the API. Partial payments will override each other, this means that if you allow for multiple payments in your accounting system, you will need to group these payments into a single payment amount per ConnectWise invoice. If the paid amount exceeds the balance due on the invoice, the paid amount will be set to the total value of the invoice and discard the overage. The payment date will not get populated until the full amount is paid.


## Settings

### Connection 
_Required_
The ConnectWise Company to Update the Invoice Payments to.	  The ConnectWise user's security role must have Edit Level access to the Accounting Interface in order to use this task.	  Click the link if you require more information on how to create/manage this type of connection.

### Fail File
_Required_
An absolute or relative file path on the local computer or network, any invoice payment updates that fail to upload to ConnectWise will be saved to this file.     	  This will be defaulted to the current working directory\connectwise\_accounting\_interface\_update\_invoice\_payments\_fail.xml.

### Input
_Required_
An absolute or relative file path on the local computer or network to the file containing Invoice Payment Update XML, or the Invoice Payment Update XML itself.  	  This will be defaulted to the 'Output from the previous task'

### Success File
_Required_
An absolute or relative file path on the local computer or network, any invoice payment updates that are successfully uploaded to ConnectWise will be saved to this file.     This will be defaulted to the current working directory\connectwise\_accounting\_interface\_update\_invoice\_payments\_success.xml.


## Examples


Sample Input:

```xml
<?xml version="1.0" encoding="utf-8"?>
    <ArrayOfUpdateInvoicePayment>
      <UpdateInvoicePayment>
        <InvoiceNumber>CW-34251</InvoiceNumber>
        <PaidAmount>346.34</PaidAmount>
        <DatePaid>2016-09-22T12:05:54+01:00</DatePaid>
      </UpdateInvoicePayment>
    </ArrayOfUpdateInvoicePayment>
```

Sample Fail File:

```xml
<?xml version="1.0"?>
    <ArrayOfUpdateInvoicePayment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <UpdateInvoicePayment>
        <InvoiceNumber>CW-34251</InvoiceNumber>
        <PaidAmount>346.34</PaidAmount>
        <DatePaid>2016-09-22T12:05:54+01:00</DatePaid>
        <ErrorMessage>Cannot find Invoice Number CW-34251</ErrorMessage>
      </UpdateInvoicePayment>
    </ArrayOfUpdateInvoicePayment>
```

Sample Success File:

```xml
<?xml version="1.0"?>
    <ArrayOfUpdateInvoicePayment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <UpdateInvoicePayment>
        <InvoiceNumber>CW-34251</InvoiceNumber>
        <PaidAmount>346.34</PaidAmount>
        <DatePaid>2016-09-22T12:05:54+01:00</DatePaid>
        <ErrorMessage>Cannot find Invoice Number CW-34251</ErrorMessage>
      </UpdateInvoicePayment>
    </ArrayOfUpdateInvoicePayment>
```