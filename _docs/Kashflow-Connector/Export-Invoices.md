---
slug: export-invoices
redirect_from: "/article/export-kashflow-invoices"
title: Export Invoices
---


This is an example of an **Invoice** download.


```xml
<?xml version="1.0"?>
<ArrayOfInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <Id xmlns="KashFlow">6666</Id>
    <InvoiceDBID xmlns="KashFlow">72655684</InvoiceDBID>
    <InvoiceNumber xmlns="KashFlow">6</InvoiceNumber>
    <InvoiceDate xmlns="KashFlow">2016-09-16T00:00:00</InvoiceDate>
    <DueDate xmlns="KashFlow">2016-09-21T00:00:00</DueDate>
    <Customer xmlns="KashFlow">JIMI01</Customer>
    <CustomerID xmlns="KashFlow">47414686</CustomerID>
    <Paid xmlns="KashFlow">0</Paid>
    <CustomerReference xmlns="KashFlow" />
    <SuppressTotal xmlns="KashFlow">0</SuppressTotal>
    <ProjectID xmlns="KashFlow">0</ProjectID>
    <CurrencyCode xmlns="KashFlow">GBP</CurrencyCode>
    <ExchangeRate xmlns="KashFlow">1.0000</ExchangeRate>
    <ReadableString xmlns="KashFlow">Invoice Number : 6 
DBID: 72655684 
Date: 16/09/2016 00:00:00 
Due: 21/09/2016 00:00:00 
Customer: JIMI01 
Paid: 0 
Cust Ref:  
Line 1 : 17387826,This is a test line for a sub product.,133251213,1.0000,8.3300,20.0000
Line 2 : 17387826,Deluxe version of Rubber Soul, the 1965 album by The Beatles.,133251214,1.0000,10.8200,20.0000
Line 3 : 17387826,This is a test line for a sales code.,133251216,1.0000,10.8200,20.0000
</ReadableString>
    <Lines xmlns="KashFlow">
      <anyType xsi:type="InvoiceLine">
        <Sku>BLONDE01</Sku>
        <SubProduct>true</SubProduct>
        <Quantity>1.0000</Quantity>
        <Description>This is a test line for a sub product.</Description>
        <Rate>8.3300</Rate>
        <ChargeType>17387826</ChargeType>
        <VatRate>20.0000</VatRate>
        <VatAmount>1.6700</VatAmount>
        <ProductID>2747099</ProductID>
        <Sort>1</Sort>
        <ProjID>0</ProjID>
        <LineID>133251213</LineID>
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
        <LineID>133251214</LineID>
      </anyType>
      <anyType xsi:type="InvoiceLine">
        <SubProduct>false</SubProduct>
        <Quantity>1.0000</Quantity>
        <Description>This is a test line for a sales code.</Description>
        <Rate>10.8200</Rate>
        <ChargeType>17387826</ChargeType>
        <VatRate>20.0000</VatRate>
        <VatAmount>2.1600</VatAmount>
        <ProductID>0</ProductID>
        <Sort>3</Sort>
        <ProjID>0</ProjID>
        <LineID>133251216</LineID>
      </anyType>
    </Lines>
    <NetAmount xmlns="KashFlow">29.9700</NetAmount>
    <VATAmount xmlns="KashFlow">5.9900</VATAmount>
    <AmountPaid xmlns="KashFlow">0.0000</AmountPaid>
    <CustomerName xmlns="KashFlow">Jimi Hendirx</CustomerName>
    <PermaLink xmlns="KashFlow">https://api.kashflow.com/v2/documents/invoice/3f2acad0-653c-4803-bb8b-8f0da9c7f2d2</PermaLink>
    <DeliveryAddress xmlns="KashFlow">
      <Name />
      <Line1 />
      <Line2 />
      <Line3 />
      <Line4 />
      <PostCode />
      <CountryName />
      <CountryCode />
    </DeliveryAddress>
    <UseCustomDeliveryAddress xmlns="KashFlow">false</UseCustomDeliveryAddress>
  </Invoice>
</ArrayOfInvoice>

```
