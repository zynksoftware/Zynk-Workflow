---
slug: exporting-all-selling-from-ebay
title: Exporting All Selling from eBay
---
This task will export all listings being sold from your eBay account. See the Examples section for a for sample output file.

## Settings
### Connection
_Required_  
The eBay connection to use. See the [Connecting to eBay](connecting-to-ebay) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The file to export the listings to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<GetMyeBaySellingResponseType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Timestamp xmlns="urn:ebay:apis:eBLBaseComponents">2019-02-14T14:31:48.174Z</Timestamp>
  <Ack xmlns="urn:ebay:apis:eBLBaseComponents">Success</Ack>
  <Version xmlns="urn:ebay:apis:eBLBaseComponents">1083</Version>
  <Build xmlns="urn:ebay:apis:eBLBaseComponents">E1083_INTL_APISELLING_18873597_R1</Build>
  <ActiveList xmlns="urn:ebay:apis:eBLBaseComponents">
    <ItemArray>
      <Item>
        <BuyItNowPrice currencyID="USD">100</BuyItNowPrice>
        <ItemID>110384701990</ItemID>
        <ListingDetails>
          <ConvertedBuyItNowPrice currencyID="GBP">77.63</ConvertedBuyItNowPrice>
          <StartTime>2018-10-25T09:51:45Z</StartTime>
          <ViewItemURL>https://cgi.sandbox.ebay.co.uk/iphone-/110384701990</ViewItemURL>
        </ListingDetails>
        <ListingDuration>GTC</ListingDuration>
        <ListingType>FixedPriceItem</ListingType>
        <Quantity>1</Quantity>
        <SellingStatus>
          <ConvertedCurrentPrice currencyID="GBP">77.63</ConvertedCurrentPrice>
          <CurrentPrice currencyID="USD">100</CurrentPrice>
        </SellingStatus>
        <ShippingDetails>
          <ShippingServiceOptions>
            <ShippingServiceCost currencyID="USD">5</ShippingServiceCost>
          </ShippingServiceOptions>
          <ShippingType>Flat</ShippingType>
        </ShippingDetails>
        <TimeLeft>PT0S</TimeLeft>
        <Title>iphone</Title>
        <QuantityAvailable>1</QuantityAvailable>
        <ClassifiedAdPayPerLeadFee currencyID="GBP">0</ClassifiedAdPayPerLeadFee>
        <SellerProfiles>
          <SellerShippingProfile>
            <ShippingProfileID>6008312000</ShippingProfileID>
            <ShippingProfileName>Flat:USPS Parcel Se($5.00),1 business day</ShippingProfileName>
          </SellerShippingProfile>
          <SellerReturnProfile>
            <ReturnProfileID>6008309000</ReturnProfileID>
            <ReturnProfileName>No returns accepted,International:No returns</ReturnProfileName>
          </SellerReturnProfile>
          <SellerPaymentProfile>
            <PaymentProfileID>6008310000</PaymentProfileID>
            <PaymentProfileName>Cash On Pickup Accepted,Visa or Master Card</PaymentProfileName>
          </SellerPaymentProfile>
        </SellerProfiles>
      </Item>
    </ItemArray>
    <PaginationResult>
      <TotalNumberOfPages>1</TotalNumberOfPages>
      <TotalNumberOfEntries>1</TotalNumberOfEntries>
    </PaginationResult>
  </ActiveList>
</GetMyeBaySellingResponseType>
```
