---
slug: import-quotes
redirect_from: "/article/import-kashflow-quotes"
title: Import Quotes
---


This task will upload **Quote** information.


```xml
<?xml version="1.0"?>
<ArrayOfQuote xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <Id xmlns="KashFlow">1234</Id>
    <InvoiceDate xmlns="KashFlow">2016-09-16T00:00:00</InvoiceDate>
    <Customer xmlns="KashFlow">JIMI01</Customer>
    <Lines xmlns="KashFlow">
      <anyType xsi:type="InvoiceLine">
        <Sku>100</Sku>
        <Quantity>1.0000</Quantity>
        <Description>1234567890</Description>
        <Rate>8.33</Rate>
        <VatRate>20</VatRate>
      </anyType>
    </Lines>
  </Invoice>
</ArrayOfQuote>
```
