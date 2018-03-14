---
slug: export-quotes
redirect_from: "/article/export-kashflow-quotes"
title: Export Quotes
---


This is an example of a **Quote** download.


```xml
<?xml version="1.0"?>
<ArrayOfQuote xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <Id xmlns="KashFlow">6666</Id>
    <InvoiceDBID xmlns="KashFlow">2309634</InvoiceDBID>
    <InvoiceNumber xmlns="KashFlow">10</InvoiceNumber>
    <InvoiceDate xmlns="KashFlow">2016-09-16T00:00:00</InvoiceDate>
    <DueDate xmlns="KashFlow">0001-01-01T00:00:00</DueDate>
    <Customer xmlns="KashFlow">JIMI01</Customer>
    <CustomerID xmlns="KashFlow">47414686</CustomerID>
    <Paid xmlns="KashFlow">0</Paid>
    <CustomerReference xmlns="KashFlow" />
    <EstimateCategory xmlns="KashFlow" />
    <SuppressTotal xmlns="KashFlow">0</SuppressTotal>
    <ProjectID xmlns="KashFlow">0</ProjectID>
    <CurrencyCode xmlns="KashFlow" />
    <ExchangeRate xmlns="KashFlow">0.0000</ExchangeRate>
    <ReadableString xmlns="KashFlow">Invoice Number : 10 
DBID: 2309634 
Date: 16/09/2016 00:00:00 
Due: 01/01/0001 00:00:00 
Customer: JIMI01 
Paid: 0 
Cust Ref:  
Line 1 : 17387826,1251346547,9213512,1.0000,8.3300,20.0000
Line 2 : 17387826,Deluxe version of Rubber Soul, the 1965 album by The Beatles.,9213513,1.0000,10.8200,20.0000
Line 3 : 17387826,Deluxe version of Rubber Soul, the 1965 album by The Beatles.,9213514,1.0000,10.8200,20.0000
</ReadableString>
    <Lines xmlns="KashFlow">
      <anyType xsi:type="InvoiceLine">
        <Sku>BLONDE01</Sku>
        <SubProduct>true</SubProduct>
        <Quantity>1.0000</Quantity>
        <Description>1251346547</Description>
        <Rate>8.3300</Rate>
        <ChargeType>17387826</ChargeType>
        <VatRate>20.0000</VatRate>
        <VatAmount>1.6700</VatAmount>
        <ProductID>2747099</ProductID>
        <Sort>1</Sort>
        <ProjID>0</ProjID>
        <LineID>9213512</LineID>
      </anyType>
      <anyType xsi:type="InvoiceLine">
        <Sku>RUBBER01</Sku>
        <SubProduct>true</SubProduct>
        <Quantity>1.0000</Quantity>
        <Description>Deluxe version of Rubber Soul, the 1965 album by The Beatles.</Description>
        <Rate>10.8200</Rate>
        <ChargeType>17387826</ChargeType>
        <VatRate>20.0000</VatRate>
        <VatAmount>2.1600</VatAmount>
        <ProductID>2745024</ProductID>
        <Sort>2</Sort>
        <ProjID>0</ProjID>
        <LineID>9213513</LineID>
      </anyType>
      <anyType xsi:type="InvoiceLine">
        <SubProduct>false</SubProduct>
        <Quantity>1.0000</Quantity>
        <Description>Deluxe version of Rubber Soul, the 1965 album by The Beatles.</Description>
        <Rate>10.8200</Rate>
        <ChargeType>17387826</ChargeType>
        <VatRate>20.0000</VatRate>
        <VatAmount>2.1600</VatAmount>
        <ProductID>0</ProductID>
        <Sort>3</Sort>
        <ProjID>0</ProjID>
        <LineID>9213514</LineID>
      </anyType>
    </Lines>
    <NetAmount xmlns="KashFlow">29.9700</NetAmount>
    <VATAmount xmlns="KashFlow">5.9900</VATAmount>
    <AmountPaid xmlns="KashFlow">0</AmountPaid>
    <PermaLink xmlns="KashFlow">https://api.kashflow.com/v2/documents/quote/8dafbed8-cb32-49b8-863b-c52c267c7c6b</PermaLink>
    <UseCustomDeliveryAddress xmlns="KashFlow">false</UseCustomDeliveryAddress>
  </Invoice>
</ArrayOfQuote>
```
