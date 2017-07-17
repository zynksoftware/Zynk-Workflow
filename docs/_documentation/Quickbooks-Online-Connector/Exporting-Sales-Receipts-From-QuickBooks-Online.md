---
slug: exporting-sales-receipts-from-quickbooks-online
redirect_from: "/article/874-downloading-sales-receipts-from-quickbooks-online"
title: Exporting Sales Receipts From QuickBooks Online
---


This task will download sales receipts from Quickbooks Online to an XML file.


## Download Sales Receipts

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
- TotalAmt
- Balance
- PaymentRefNum

## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfSalesReceipt xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfSalesReceipt>
        <ExternalId>8245</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>180</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-07-07T16:11:13+01:00</CreateTime>
            <LastUpdatedTime>2016-07-07T16:11:13+01:00</LastUpdatedTime>
          </MetaData>
          <DocNumber>1018</DocNumber>
          <TxnDate>2016-07-07T00:00:00</TxnDate>
          <CurrencyRef name="British Pound Sterling">GBP</CurrencyRef>
          <ExchangeRate>1</ExchangeRate>
          <PrivateNote>this is a memo</PrivateNote>
          <Line>
            <Id>1</Id>
            <LineNum>1</LineNum>
            <Description>Catering -- food &amp;amp; beverage</Description>
            <Amount>50</Amount>
            <DetailType>SalesItemLineDetail</DetailType>
            <SalesItemLineDetail>
              <ItemRef name="Catering">3</ItemRef>
              <UnitPrice>50</UnitPrice>
              <Qty>1</Qty>
              <TaxCodeRef>3</TaxCodeRef>
            </SalesItemLineDetail>
          </Line>
          <Line>
            <Amount>50</Amount>
            <DetailType>SubTotalLineDetail</DetailType>
            <SubTotalLineDetail />
          </Line>
          <TxnTaxDetail>
            <TotalTax>10</TotalTax>
            <TaxLine>
              <Amount>10</Amount>
              <DetailType>TaxLineDetail</DetailType>
              <TaxLineDetail>
                <TaxRateRef>4</TaxRateRef>
                <PercentBased>true</PercentBased>
                <TaxPercent>20</TaxPercent>
                <NetAmountTaxable>50</NetAmountTaxable>
              </TaxLineDetail>
            </TaxLine>
          </TxnTaxDetail>
          <CustomerRef name="Zynk Software">2068</CustomerRef>
          <CustomerMemo>this is a message</CustomerMemo>
          <BillAddr>
            <Id>77</Id>
            <Line1>Zynk Software</Line1>
            <Line2>Nelson House</Line2>
            <Line3>Jesmond</Line3>
            <City>Newcastle</City>
            <Country>England</Country>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <ShipAddr>
            <Id>78</Id>
            <Line1>Zynk Software</Line1>
            <Line2>Nelson House</Line2>
            <Line3>Jesmond</Line3>
            <City>Newcastle</City>
            <Country>England</Country>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </ShipAddr>
          <GlobalTaxCalculation>TaxExcluded</GlobalTaxCalculation>
          <TotalAmt>60</TotalAmt>
          <HomeTotalAmt>60</HomeTotalAmt>
          <PrintStatus>NeedToPrint</PrintStatus>
          <EmailStatus>NotSet</EmailStatus>
          <BillEmail>
            <Address>support@zynk.com</Address>
          </BillEmail>
          <Balance>0</Balance>
          <HomeBalance>0</HomeBalance>
          <PaymentRefNum>abc123</PaymentRefNum>
          <DepositToAccountRef name="Undeposited Funds">84</DepositToAccountRef>
        </Data>
      </RecordOfSalesReceipt>
    </ArrayOfSalesReceipt>

```