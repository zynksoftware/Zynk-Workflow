---
slug: sage-50-uk-update-ledger-xml
title: Sage 50 UK Update Ledger XML
---
The Update Ledgers task allows you to post invoices in Sage 50, which will create the relevant transactions against the customer account and update the customer's balance. 

Any fields not documented below are not directly supported with our imports.

## Selecting an Invoice
The only fields that need to provided when using this task are those that identify the invoices to post. Any other invoice fields provided in the XML will be ignored.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | Id | 123 | string | -  | Dependant | Must be specified if InvoiceNumber is not provided. This field will be ignored if InvoiceNumber is provided. Matching based on Id will only work if the invoice was created using Zynk, and the same Id was used at the time of the import. |
| Inv. No. | InvoiceNumber | 2352 | string  | 7 | Dependant | Must be specified if Id is not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoices>
    <Invoice>
      <Id>123</Id>
      <InvoiceNumber>2352</InvoiceNumber>
    </Invoice>
  </Invoices>
</Company>
```