---
slug: import-purchases
redirect_from: "/article/import-kashflow-purchases"
title: Import Purchases
---


This task will upload **Purchase**information.


```xml
<?xml version="1.0"?>
<ArrayOfPurchase xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <Id xmlns="KashFlow">0000</Id>
    <Customer xmlns="KashFlow">RING01</Customer>
    <Lines xmlns="KashFlow">
      <anyType xsi:type="InvoiceLine">
        <ChargeType>17387829</ChargeType>
        <Description>Test...</Description>
        <Quantity>1.0000</Quantity>
        <Rate>8.33</Rate>
        <VatRate>20</VatRate>
        <SubProduct>false</SubProduct>
      </anyType>
    </Lines>
  </Invoice>
</ArrayOfPurchase><br>
```
