---
slug: export-purchases
redirect_from: "/article/export-kashflow-purchases"
title: Export Purchases
---


This is an example of a **Purchase** download.


```xml
<?xml version="1.0"?>
<ArrayOfPurchase xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <InvoiceDBID xmlns="KashFlow">45741079</InvoiceDBID>
    <InvoiceNumber xmlns="KashFlow">1</InvoiceNumber>
    <InvoiceDate xmlns="KashFlow">2016-09-20T00:00:00</InvoiceDate>
    <DueDate xmlns="KashFlow">2016-10-20T00:00:00</DueDate>
    <Customer xmlns="KashFlow">PAUL01</Customer>
    <CustomerID xmlns="KashFlow">5468649</CustomerID>
    <Paid xmlns="KashFlow">0</Paid>
    <CustomerReference xmlns="KashFlow" />
    <SuppressTotal xmlns="KashFlow">0</SuppressTotal>
    <ProjectID xmlns="KashFlow">0</ProjectID>
    <CurrencyCode xmlns="KashFlow">GBP</CurrencyCode>
    <ExchangeRate xmlns="KashFlow">1.0000</ExchangeRate>
    <ReadableString xmlns="KashFlow">Invoice Number : 1 
DBID: 45741079 
Date: 20/09/2016 00:00:00 
Due: 20/10/2016 00:00:00 
Customer: PAUL01 
Paid: 0 
Cust Ref:  
Line 1 : 17387829,5156547568,56293159,1.0000,8.3300,20.0000
</ReadableString>
    <Lines xmlns="KashFlow">
      <anyType xsi:type="InvoiceLine">
        <Sku>TEST01</Sku>
        <SubProduct>true</SubProduct>
        <Quantity>1.0000</Quantity>
        <Description>5156547568</Description>
        <Rate>8.3300</Rate>
        <ChargeType>17387829</ChargeType>
        <VatRate>20.0000</VatRate>
        <VatAmount>1.6700</VatAmount>
        <ProductID>2747368</ProductID>
        <Sort>1</Sort>
        <ProjID>0</ProjID>
        <LineID>56293159</LineID>
      </anyType>
    </Lines>
    <NetAmount xmlns="KashFlow">8.3300</NetAmount>
    <VATAmount xmlns="KashFlow">1.6700</VATAmount>
    <AmountPaid xmlns="KashFlow">0.0000</AmountPaid>
    <CustomerName xmlns="KashFlow">Paul McCartney</CustomerName>
    <UseCustomDeliveryAddress xmlns="KashFlow">false</UseCustomDeliveryAddress>
  </Invoice>
</ArrayOfPurchase>
```
