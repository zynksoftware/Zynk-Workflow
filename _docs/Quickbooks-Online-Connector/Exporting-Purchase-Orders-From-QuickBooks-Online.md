---
slug: exporting-purchase-orders-from-quickbooks-online
redirect_from: "/article/873-downloading-purchase-orders-from-quickbooks-online"
title: Exporting Purchase Orders From QuickBooks Online
---


This task will download purchase orders from Quickbooks Online to an XML file.


## Download Purchase Orders

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
- APAccountRef
- DueDate


## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfPurchaseOrder>
        <ExternalId>3794</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>17</Id>
          <SyncToken>3</SyncToken>
          <MetaData>
            <CreateTime>2016-04-19T17:18:38+01:00</CreateTime>
            <LastUpdatedTime>2016-04-20T22:18:49+01:00</LastUpdatedTime>
          </MetaData>
          <DocNumber>1002</DocNumber>
          <TxnDate>2015-07-29T00:00:00</TxnDate>
          <CurrencyRef name="Hong Kong Dollar">HKD</CurrencyRef>
          <ExchangeRate>0.080028</ExchangeRate>
          <LinkedTxn>
            <TxnId>157</TxnId>
            <TxnType>Bill</TxnType>
          </LinkedTxn>
          <Line>
            <Id>1</Id>
            <Description>Water bottles -- generic</Description>
            <Amount>6617.17</Amount>
            <DetailType>ItemBasedExpenseLineDetail</DetailType>
            <ItemBasedExpenseLineDetail>
              <ItemRef name="Water Bottles">19</ItemRef>
              <UnitPrice>66.1717023</UnitPrice>
              <Qty>100</Qty>
              <TaxCodeRef>3</TaxCodeRef>
              <CustomerRef name="Oxon Insurance Agency:Oxon - Holiday Party">55</CustomerRef>
              <BillableStatus>NotBillable</BillableStatus>
            </ItemBasedExpenseLineDetail>
          </Line>
          <TxnTaxDetail>
            <TaxLine>
              <Amount>1323.43</Amount>
              <DetailType>TaxLineDetail</DetailType>
              <TaxLineDetail>
                <TaxRateRef>3</TaxRateRef>
                <PercentBased>true</PercentBased>
                <TaxPercent>20</TaxPercent>
                <NetAmountTaxable>6617.17</NetAmountTaxable>
              </TaxLineDetail>
            </TaxLine>
          </TxnTaxDetail>
          <VendorRef name="Hall's Promo Items">57</VendorRef>
          <APAccountRef name="Creditors">71</APAccountRef>
          <TotalAmt>7940.6</TotalAmt>
          <GlobalTaxCalculation>TaxExcluded</GlobalTaxCalculation>
          <ShipAddr>
            <Id>57</Id>
            <Line1>Long for Successful Events -- Sample Company</Line1>
            <Line2>2500 Garcia Ave</Line2>
            <Line3>SomeCity</Line3>
            <Line4>CR2 6XH</Line4>
            <Lat>INVALID</Lat>
            <Long>INVALID</Long>
          </ShipAddr>
          <POStatus>Closed</POStatus>
        </Data>
      </RecordOfPurchaseOrder>
    </ArrayOfPurchaseOrder>

```