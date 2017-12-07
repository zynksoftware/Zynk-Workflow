---
slug: downloading-listings-from-ebay
redirect_from: "/article/215-downloading-listings-from-ebay"
title: Downloading Listings from eBay
---
This task will export listings information from eBay in XML format.

## Settings
### Connection
_Required_  
The eBay connection to use. See the [Connecting to eBay](connecting-to-ebay) article if you require more information on how to create/manage connections.

### Export Date
_Required_  
The date to export listings to.

### Export From
_Required_  
The date to export listings from.

### Include Variations
_Required_  
Allows you to export extended variant / option information about the listings. Defaults to False.

### Output File
_Required_  
The name of the file to export the listings to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0"?>
<GetSellerListResponseType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Timestamp xmlns="urn:ebay:apis:eBLBaseComponents">2016-02-17T16:44:31.229Z</Timestamp>
  <Ack xmlns="urn:ebay:apis:eBLBaseComponents">Success</Ack>
  <Version xmlns="urn:ebay:apis:eBLBaseComponents">949</Version>
  <Build xmlns="urn:ebay:apis:eBLBaseComponents">E949_INTL_API_17790382_R1</Build>
  <PaginationResult xmlns="urn:ebay:apis:eBLBaseComponents">
    <TotalNumberOfPages>1</TotalNumberOfPages>
    <TotalNumberOfEntries>1</TotalNumberOfEntries>
  </PaginationResult>
  <HasMoreItems xmlns="urn:ebay:apis:eBLBaseComponents">false</HasMoreItems>
  <ItemArray xmlns="urn:ebay:apis:eBLBaseComponents">
    <Item>
      <AutoPay>false</AutoPay>
      <BuyerProtection>ItemIneligible</BuyerProtection>
      <BuyItNowPrice currencyID="GBP">50</BuyItNowPrice>
      <Country>GB</Country>
      <Currency>GBP</Currency>
      <Description><font size="2"><font face="Arial">jeans</font></font></Description>
      <GiftIcon>0</GiftIcon>
      <HitCounter>NoHitCounter</HitCounter>
      <ItemID>110173857452</ItemID>
      <ListingDetails>
        <Adult>false</Adult>
        <BindingAuction>false</BindingAuction>
        <CheckoutEnabled>true</CheckoutEnabled>
        <ConvertedBuyItNowPrice currencyID="GBP">50</ConvertedBuyItNowPrice>
        <ConvertedStartPrice currencyID="GBP">0.99</ConvertedStartPrice>
        <ConvertedReservePrice currencyID="GBP">0</ConvertedReservePrice>
        <HasReservePrice>false</HasReservePrice>
        <StartTime>2016-02-17T16:44:00Z</StartTime>
        <EndTime>2016-02-27T16:44:00Z</EndTime>
        <ViewItemURL>http://cgi.sandbox.ebay.co.uk/Levis-501-womens-jeans-/110173857452</ViewItemURL>
        <HasUnansweredQuestions>false</HasUnansweredQuestions>
        <HasPublicMessages>false</HasPublicMessages>
        <BuyItNowAvailable>true</BuyItNowAvailable>
        <ViewItemURLForNaturalSearch>http://cgi.sandbox.ebay.co.uk/Levis-501-womens-jeans-/110173857452</ViewItemURLForNaturalSearch>
      </ListingDetails>
      <ListingDesigner>
        <LayoutID>310000</LayoutID>
        <ThemeID>310</ThemeID>
      </ListingDesigner>
      <ListingDuration>Days_10</ListingDuration>
      <ListingType>Chinese</ListingType>
      <Location>city, BUCKINGHAMSHIRE</Location>
      <PaymentMethods>PayPal</PaymentMethods>
      <PayPalEmailAddress>support@zynk.co.uk</PayPalEmailAddress>
      <PrimaryCategory>
        <CategoryID>11554</CategoryID>
        <CategoryName>Clothes, Shoes & Accessories:Women's Clothing:Jeans</CategoryName>
      </PrimaryCategory>
      <PrivateListing>false</PrivateListing>
      <Quantity>1</Quantity>
      <ReservePrice currencyID="GBP">0</ReservePrice>
      <ReviseStatus>
        <ItemRevised>false</ItemRevised>
      </ReviseStatus>
      <SellingStatus>
        <BidCount>0</BidCount>
        <BidIncrement currencyID="GBP">0.05</BidIncrement>
        <ConvertedCurrentPrice currencyID="GBP">0.99</ConvertedCurrentPrice>
        <CurrentPrice currencyID="GBP">0.99</CurrentPrice>
        <LeadCount>0</LeadCount>
        <MinimumToBid currencyID="GBP">0.99</MinimumToBid>
        <QuantitySold>0</QuantitySold>
        <ReserveMet>true</ReserveMet>
        <SecondChanceEligible>false</SecondChanceEligible>
        <ListingStatus>Active</ListingStatus>
      </SellingStatus>
      <ShippingDetails>
        <ApplyShippingDiscount>false</ApplyShippingDiscount>
        <CalculatedShippingRate>
          <WeightMajor unit="kg" measurementSystem="Metric">0</WeightMajor>
          <WeightMinor unit="gm" measurementSystem="Metric">0</WeightMinor>
        </CalculatedShippingRate>
        <SalesTax>
          <SalesTaxPercent>0</SalesTaxPercent>
          <ShippingIncludedInTax>false</ShippingIncludedInTax>
        </SalesTax>
        <ShippingServiceOptions>
          <ShippingService>UK_RoyalMailSecondClassStandard</ShippingService>
          <ShippingServiceCost currencyID="GBP">2.5</ShippingServiceCost>
          <ShippingServicePriority>1</ShippingServicePriority>
          <ExpeditedService>false</ExpeditedService>
          <ShippingTimeMin>2</ShippingTimeMin>
          <ShippingTimeMax>3</ShippingTimeMax>
        </ShippingServiceOptions>
        <ShippingType>Flat</ShippingType>
        <ThirdPartyCheckout>false</ThirdPartyCheckout>
        <ShippingDiscountProfileID>0</ShippingDiscountProfileID>
        <InternationalShippingDiscountProfileID>0</InternationalShippingDiscountProfileID>
        <SellerExcludeShipToLocationsPreference>false</SellerExcludeShipToLocationsPreference>
      </ShippingDetails>
      <ShipToLocations>GB</ShipToLocations>
      <Site>UK</Site>
      <StartPrice currencyID="GBP">0.99</StartPrice>
      <TimeLeft>P9DT23H59M29S</TimeLeft>
      <Title>Levis 501 women's jeans</Title>
      <WatchCount>0</WatchCount>
      <GetItFast>false</GetItFast>
      <PostalCode>HP19 3EQ</PostalCode>
      <PictureDetails>
        <PhotoDisplay>None</PhotoDisplay>
      </PictureDetails>
      <DispatchTimeMax>3</DispatchTimeMax>
      <ProxyItem>false</ProxyItem>
      <BuyerGuaranteePrice currencyID="GBP">20000</BuyerGuaranteePrice>
      <BuyerRequirementDetails>
        <ShipToRegistrationCountry>true</ShipToRegistrationCountry>
        <MinimumFeedbackScore>-1</MinimumFeedbackScore>
        <MaximumUnpaidItemStrikesInfo>
          <Count>2</Count>
          <Period>Days_30</Period>
        </MaximumUnpaidItemStrikesInfo>
      </BuyerRequirementDetails>
      <ReturnPolicy>
        <ReturnsAcceptedOption>ReturnsNotAccepted</ReturnsAcceptedOption>
        <ReturnsAccepted>Returns Not Accepted</ReturnsAccepted>
      </ReturnPolicy>
      <PaymentAllowedSite>UK</PaymentAllowedSite>
      <PaymentAllowedSite>Ireland</PaymentAllowedSite>
      <ConditionID>1000</ConditionID>
      <ConditionDisplayName>New with tags</ConditionDisplayName>
      <PostCheckoutExperienceEnabled>false</PostCheckoutExperienceEnabled>
      <SellerProfiles />
      <ShippingPackageDetails>
        <ShippingIrregular>false</ShippingIrregular>
        <ShippingPackage>PackageThickEnvelope</ShippingPackage>
        <WeightMajor unit="kg" measurementSystem="Metric">0</WeightMajor>
        <WeightMinor unit="gm" measurementSystem="Metric">0</WeightMinor>
      </ShippingPackageDetails>
      <HideFromSearch>false</HideFromSearch>
      <eBayPlus>false</eBayPlus>
      <eBayPlusEligible>false</eBayPlusEligible>
    </Item>
  </ItemArray>
  <ItemsPerPage xmlns="urn:ebay:apis:eBLBaseComponents">10</ItemsPerPage>
  <PageNumber xmlns="urn:ebay:apis:eBLBaseComponents">1</PageNumber>
  <ReturnedItemCountActual xmlns="urn:ebay:apis:eBLBaseComponents">1</ReturnedItemCountActual>
  <Seller xmlns="urn:ebay:apis:eBLBaseComponents">
    <AboutMePage>false</AboutMePage>
    <Email>support@zynk.co.uk</Email>
    <FeedbackScore>500</FeedbackScore>
    <PositiveFeedbackPercent>0</PositiveFeedbackPercent>
    <FeedbackPrivate>false</FeedbackPrivate>
    <FeedbackRatingStar>Purple</FeedbackRatingStar>
    <IDVerified>true</IDVerified>
    <eBayGoodStanding>true</eBayGoodStanding>
    <NewUser>false</NewUser>
    <RegistrationDate>2010-01-01T00:00:00Z</RegistrationDate>
    <Site>UK</Site>
    <Status>Confirmed</Status>
    <UserID>testuser_adamwardle</UserID>
    <UserIDChanged>false</UserIDChanged>
    <UserIDLastChanged>2013-01-10T11:15:27Z</UserIDLastChanged>
    <VATStatus>VATTax</VATStatus>
    <SellerInfo>
      <AllowPaymentEdit>false</AllowPaymentEdit>
      <CheckoutEnabled>true</CheckoutEnabled>
      <CIPBankAccountStored>false</CIPBankAccountStored>
      <GoodStanding>true</GoodStanding>
      <MerchandizingPref>OptIn</MerchandizingPref>
      <QualifiesForB2BVAT>false</QualifiesForB2BVAT>
      <StoreOwner>false</StoreOwner>
      <SafePaymentExempt>false</SafePaymentExempt>
      <LiveAuctionAuthorized>false</LiveAuctionAuthorized>
    </SellerInfo>
    <MotorsDealer>false</MotorsDealer>
  </Seller>
</GetSellerListResponseType>
```
