---
slug: exporting-invoices-from-quickbooks-online
redirect_from: "/article/870-downloading-invoices-from-quickbooks-online"
title: Exporting Invoices From QuickBooks Online
---


This task will download invoices from Quickbooks Online to an XML file.


## Download Invoices

### Connection
_Required_  
Select a connection to the Quickbooks Online company you want to use. See [Connecting to QuickBooks Online](connecting-to-quickbooks-online)

### Output File
_Required_  
The file save exported records to.

### Quickbooks Online Settings
See [Common Quickbooks Online Settings](common-quickbooks-online-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Available Filters
- Id
- DocNumber
- TxnDate
- CustomerRef
- SalesTermRef
- DueDate
- Balance

## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfInvoice>
        <ExternalId>452</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>183</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-07-18T11:49:20+01:00</CreateTime>
            <LastUpdatedTime>2016-07-18T11:49:20+01:00</LastUpdatedTime>
          </MetaData>
          <DocNumber>1021</DocNumber>
          <TxnDate>2016-07-18T00:00:00</TxnDate>
          <CurrencyRef name="British Pound Sterling">GBP</CurrencyRef>
          <ExchangeRate>1</ExchangeRate>
          <Line>
            <Id>1</Id>
            <LineNum>1</LineNum>
            <Description>Employee training off site</Description>
            <Amount>1000</Amount>
            <DetailType>SalesItemLineDetail</DetailType>
            <SalesItemLineDetail>
              <ItemRef name="Employee Training">5</ItemRef>
              <UnitPrice>1000</UnitPrice>
              <Qty>1</Qty>
              <TaxCodeRef>3</TaxCodeRef>
            </SalesItemLineDetail>
          </Line>
          <Line>
            <Amount>1000</Amount>
            <DetailType>SubTotalLineDetail</DetailType>
            <SubTotalLineDetail />
          </Line>
          <TxnTaxDetail>
            <TotalTax>200</TotalTax>
            <TaxLine>
              <Amount>200</Amount>
              <DetailType>TaxLineDetail</DetailType>
              <TaxLineDetail>
                <TaxRateRef>4</TaxRateRef>
                <PercentBased>true</PercentBased>
                <TaxPercent>20</TaxPercent>
                <NetAmountTaxable>1000</NetAmountTaxable>
              </TaxLineDetail>
            </TaxLine>
          </TxnTaxDetail>
          <CustomerRef name="Zynk Software">2068</CustomerRef>
          <BillAddr>
            <Id>83</Id>
            <Line1>Zynk Software</Line1>
            <Line2>Nelson House</Line2>
            <Line3>Jesmond</Line3>
            <City>Newcastle</City>
            <Country>England</Country>
            <CountrySubDivisionCode>Tyne &amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <ShipAddr>
            <Id>84</Id>
            <Line1>Zynk Software</Line1>
            <Line2>Nelson House</Line2>
            <Line3>Jesmond</Line3>
            <City>Newcastle</City>
            <Country>England</Country>
            <CountrySubDivisionCode>Tyne &amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </ShipAddr>
          <SalesTermRef>3</SalesTermRef>
          <DueDate>2016-08-17T00:00:00</DueDate>
          <GlobalTaxCalculation>TaxExcluded</GlobalTaxCalculation>
          <TotalAmt>1200</TotalAmt>
          <HomeTotalAmt>1200</HomeTotalAmt>
          <PrintStatus>NeedToPrint</PrintStatus>
          <EmailStatus>NotSet</EmailStatus>
          <Balance>1200</Balance>
          <HomeBalance>1200</HomeBalance>
          <Deposit>0</Deposit>
          <AllowIPNPayment>false</AllowIPNPayment>
          <AllowOnlinePayment>false</AllowOnlinePayment>
          <AllowOnlineCreditCardPayment>false</AllowOnlineCreditCardPayment>
          <AllowOnlineACHPayment>false</AllowOnlineACHPayment>
        </Data>
      </RecordOfInvoice>
    </ArrayOfInvoice>

```