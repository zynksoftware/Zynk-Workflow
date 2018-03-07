---
slug: import-invoices
redirect_from: "/article/import-kashflow-invoices"
title: Import Invoices
---


This task will upload **Invoice** information.


```xml
<?xml version="1.0"?>
<ArrayOfInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <Id xmlns="KashFlow">6666</Id>
    <InvoiceDate xmlns="KashFlow">2016-09-16T00:00:00</InvoiceDate>
    <Customer xmlns="KashFlow">JIMI01</Customer>
    <Lines xmlns="KashFlow">
      <anyType xsi:type="InvoiceLine">
        <Sku>100</Sku>
        <Quantity>1.0000</Quantity>
        <Description>This is a test line for a sales code.</Description>
        <Rate>10.8200</Rate>
        <VatRate>20.0000</VatRate>
        <SubProduct>false</SubProduct>
      </anyType>
    </Lines>
  </Invoice>
</ArrayOfInvoice>
```
