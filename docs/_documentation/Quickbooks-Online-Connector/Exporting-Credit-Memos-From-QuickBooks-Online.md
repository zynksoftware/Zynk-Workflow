---
slug: exporting-credit-memos-from-quickbooks-online
redirect_from: "/article/867-downloading-credit-memos-from-quickbooks-online"
title: Exporting Credit Memos From QuickBooks Online
---


This task will download credit memos from Quickbooks Online to an XML file.


## Download Credit Memos

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
- Balance


## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfCreditMemo>
        <ExternalId>34</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>181</Id>
          <SyncToken>0</SyncToken>
          <MetaData>
            <CreateTime>2016-07-07T16:29:29+01:00</CreateTime>
            <LastUpdatedTime>2016-07-07T16:29:29+01:00</LastUpdatedTime>
          </MetaData>
          <DocNumber>1019</DocNumber>
          <TxnDate>2016-07-07T00:00:00</TxnDate>
          <CurrencyRef name="British Pound Sterling">GBP</CurrencyRef>
          <ExchangeRate>1</ExchangeRate>
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
          <BillAddr>
            <Id>79</Id>
            <Line1>Zynk Software</Line1>
            <Line2>Nelson House</Line2>
            <Line3>Jesmond</Line3>
            <City>Newcastle</City>
            <Country>England</Country>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <ShipAddr>
            <Id>80</Id>
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
          <PrintStatus>NotSet</PrintStatus>
          <EmailStatus>NeedToSend</EmailStatus>
          <BillEmail>
            <Address>support@zynk.com</Address>
          </BillEmail>
          <Balance>60</Balance>
          <HomeBalance>60</HomeBalance>
          <DeliveryInfo>
            <DeliveryType>Email</DeliveryType>
          </DeliveryInfo>
          <RemainingCredit>60</RemainingCredit>
        </Data>
      </RecordOfCreditMemo>
    </ArrayOfCreditMemo>

```