---
slug: downloading-transactions-from-paypal
redirect_from: "/article/282-downloading-transactions-from-paypal"
title: Downloading Transactions from Paypal
---
The Download transactions task will download all PayPal transactions between the specified Start and End Date to the desired Output File in XML format. The Output Details option instructs the task to download additional transaction details including order item lines where specified.

The Start Date and End Date are updated after the task runs to the current Date Time and the current Date Time plus one day.

## Settings
### Start Date
_Required_  
Start Date for date range (Defaults to Current Date)

### End Date
_Required_  
End Date for date range (Defaults to Current Date + 1 Day

### Output Details
_Required_  
Set to True to show all order line details or False to output header details only

### Output File
_Required_  
Name of PayPal transaction XML file to be created

### PayPal API Environment
_Required_  
Leave blank for Live mode or set to Sandbox or Live

### PayPal API Password
_Required_  
Password for PayPal API access

### PayPal API Signature
_Required_  
Signature for PayPal API access

### PayPal API Username
_Required_  
Username for PayPal API access

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Sample Output
### Headers Only

```xml
<?xml version="1.0"?>
<TransactionSearchResponseType>
  <Timestamp xmlns="urn:ebay:apis:eBLBaseComponents">2011-03-10T15:10:30Z</Timestamp>
  <Ack xmlns="urn:ebay:apis:eBLBaseComponents">Success</Ack>
  <CorrelationID xmlns="urn:ebay:apis:eBLBaseComponents">cd4fcc385ff0b</CorrelationID>
  <Version xmlns="urn:ebay:apis:eBLBaseComponents">54.0</Version>
  <Build xmlns="urn:ebay:apis:eBLBaseComponents">1776465</Build>
  <PaymentTransactions xmlns="urn:ebay:apis:eBLBaseComponents">
    <Timestamp>2009-04-23T12:38:49Z</Timestamp>
    <Timezone>GMT</Timezone>
    <Type>Payment</Type>
    <Payer>delete-69612932YR098131C@sandbox.paypal.com</Payer>
    <PayerDisplayName>Test User</PayerDisplayName>
    <TransactionID>7UP42315GN119130H</TransactionID>
    <Status>Completed</Status>
    <GrossAmount currencyID="GBP">46.27</GrossAmount>
    <FeeAmount currencyID="GBP">-2.00</FeeAmount>
    <NetAmount currencyID="GBP">44.27</NetAmount>
  </PaymentTransactions>
 </TransactionSearchResponseType>	
 ```

### Detailed Output

```xml
<?xml version="1.0"?>
<ArrayOfGetTransactionDetailsResponseType>
  <GetTransactionDetailsResponseType>
    <Timestamp xmlns="urn:ebay:apis:eBLBaseComponents">2011-03-10T15:10:59Z</Timestamp>
    <Ack xmlns="urn:ebay:apis:eBLBaseComponents">Success</Ack>
    <CorrelationID xmlns="urn:ebay:apis:eBLBaseComponents">e19cdbe5eef48</CorrelationID>
    <Version xmlns="urn:ebay:apis:eBLBaseComponents">54.0</Version>
    <Build xmlns="urn:ebay:apis:eBLBaseComponents">1776465</Build>
    <PaymentTransactionDetails xmlns="urn:ebay:apis:eBLBaseComponents">
      <ReceiverInfo>
        <Business />
        <Receiver>delete-1L84721699792631P@sandbox.paypal.com</Receiver>
        <ReceiverID>NA56ELKJ8K9S2</ReceiverID>
      </ReceiverInfo>
      <PayerInfo>
        <Payer>delete-69612932YR098131C@sandbox.paypal.com</Payer>
        <PayerID>DGX82R296PS38</PayerID>
        <PayerStatus>verified</PayerStatus>
        <PayerName>
          <Salutation />
          <FirstName>Test</FirstName>
          <MiddleName />
          <LastName>User</LastName>
          <Suffix />
        </PayerName>
        <PayerCountry>US</PayerCountry>
        <PayerBusiness />
        <Address>
          <Name>Test User</Name>
          <Street1>1 Main St</Street1>
          <Street2 />
          <CityName>San Jose</CityName>
          <StateOrProvince>CA</StateOrProvince>
          <Country>US</Country>
          <CountryName>United States</CountryName>
          <PostalCode>95131</PostalCode>
          <AddressOwner>PayPal</AddressOwner>
          <AddressStatus>Confirmed</AddressStatus>
        </Address>
        <ContactPhone />
      </PayerInfo>
      <PaymentInfo>
        <TransactionID>7UP42315GN119130H</TransactionID>
        <ParentTransactionID />
        <ReceiptID />
        <TransactionType>express-checkout</TransactionType>
        <PaymentType>instant</PaymentType>
        <PaymentDate>2009-04-23T12:38:49Z</PaymentDate>
        <GrossAmount currencyID="GBP">46.27</GrossAmount>
        <FeeAmount currencyID="GBP">2.00</FeeAmount>
        <TaxAmount currencyID="GBP">0.00</TaxAmount>
        <ExchangeRate />
        <PaymentStatus>Completed</PaymentStatus>
        <PendingReason>none</PendingReason>
        <ReasonCode>none</ReasonCode>
        <ProtectionEligibility>Eligible</ProtectionEligibility>
      </PaymentInfo>
      <PaymentItemInfo>
        <InvoiceID />
        <Custom />
        <Memo />
        <SalesTax>0.00</SalesTax>
        <PaymentItem>
          <Name />
          <Number />
          <Quantity>1</Quantity>
          <SalesTax>0.00</SalesTax>
        </PaymentItem>
        <Subscription reattempt="" recurring="">
          <SubscriptionID />
          <Username />
          <Password />
          <Recurrences />
        </Subscription>
        <Auction multiItem="">
          <BuyerID />
        </Auction>
      </PaymentItemInfo>
    </PaymentTransactionDetails>
  </GetTransactionDetailsResponseType>
</ArrayOfGetTransactionDetailsResponseType>	
```