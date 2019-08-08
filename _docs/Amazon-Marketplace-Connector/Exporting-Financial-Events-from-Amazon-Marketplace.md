---
slug: exporting-financial-events-from-amazon-marketplace
title: Exporting Financial Events from Amazon Marketplace
---
This task will export a list of financial events in XML format from a specified Amazon MWS account based on the settings provided. Note events older than 18 months before the current date are not returned.

## Amazon Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Channels
_Required_  
Choose at least one marketplace to send the XML feed to. For information about how Amazon handles feeds sent to multiple marketplaces, see [Using Multiple Marketplaces](http://docs.developer.amazonservices.com/en_UK/feeds/Feeds_EU_Global_Seller.html).

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

## Export Settings
### Export From
_Required_  
The rolling date to download commissions from. This will automatically update each time the task runs. TIP: If you want to re-download old commissions, change the Download From property

### Export To > Download To Date
_Optional_  
Download records up to this date, required if 'Download to Enabled' is enabled.

### Export To > Download To Enabled
_Required_  
Set to true to only download records up to a certain date, if disabled will download records up to the current date.

### Order IDs
_Optional_  
If you want to get the commission for specific orders, enter the order IDs here. If there is more than one ID, they can be provided as a comma separated list.

### Output File
_Required_  
The name of the file to export the downloaded refunds to.

## Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
The following event types may be returned: -
 * ShipmentEventList
 * RefundEventList
 * GuaranteeClaimEventList
 * ChargebackEventList
 * PayWithAmazonEventList
 * ServiceProviderCreditEventList
 * RetrochargeEventList
 * RentalTransactionEventList
 * PerformanceBondRefundEventList
 * ProductAdsPaymentEventList
 * ServiceFeeEventList
 * DebtRecoveryEventList
 * LoanServicingEventList
 * AdjustmentEventList
 * CouponPaymentEventList
 * SAFETReimbursementEventList
 * SellerReviewEnrollmentPaymentEventList
 * FBALiquidationEventList
 * ImagingServicesFeeEventList
 * AffordabilityExpenseEventList
 * AffordabilityExpenseReversalEventList
 * NetworkComminglingTransactionEventList

Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<FinancialEvents xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ShipmentEventList>
    <ShipmentEvent>
      <AmazonOrderId>105-0457358-1245022</AmazonOrderId>
      <MarketplaceName>Amazon.com</MarketplaceName>
      <OrderChargeList />
      <OrderChargeAdjustmentList />
      <ShipmentFeeList />
      <ShipmentFeeAdjustmentList />
      <OrderFeeList />
      <OrderFeeAdjustmentList />
      <DirectPaymentList />
      <PostedDate>2017-01-23T01:31:25Z</PostedDate>
      <ShipmentItemList>
        <ShipmentItem>
          <SellerSKU>HS223A-C00</SellerSKU>
          <OrderItemId>46432915698730</OrderItemId>
          <QuantityShipped>1</QuantityShipped>
          <ItemChargeList>
            <ChargeComponent>
              <ChargeType>Principal</ChargeType>
              <ChargeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>2.99</CurrencyAmount>
              </ChargeAmount>
            </ChargeComponent>
            <ChargeComponent>
              <ChargeType>Tax</ChargeType>
              <ChargeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </ChargeAmount>
            </ChargeComponent>
            <ChargeComponent>
              <ChargeType>GiftWrap</ChargeType>
              <ChargeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </ChargeAmount>
            </ChargeComponent>
            <ChargeComponent>
              <ChargeType>GiftWrapTax</ChargeType>
              <ChargeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </ChargeAmount>
            </ChargeComponent>
            <ChargeComponent>
              <ChargeType>ShippingCharge</ChargeType>
              <ChargeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </ChargeAmount>
            </ChargeComponent>
            <ChargeComponent>
              <ChargeType>ShippingTax</ChargeType>
              <ChargeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </ChargeAmount>
            </ChargeComponent>
          </ItemChargeList>
          <ItemChargeAdjustmentList />
          <ItemFeeList>
            <FeeComponent>
              <FeeType>Commission</FeeType>
              <FeeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>-0.25</CurrencyAmount>
              </FeeAmount>
            </FeeComponent>
            <FeeComponent>
              <FeeType>FixedClosingFee</FeeType>
              <FeeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </FeeAmount>
            </FeeComponent>
            <FeeComponent>
              <FeeType>GiftwrapCommission</FeeType>
              <FeeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </FeeAmount>
            </FeeComponent>
            <FeeComponent>
              <FeeType>ShippingHB</FeeType>
              <FeeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </FeeAmount>
            </FeeComponent>
            <FeeComponent>
              <FeeType>VariableClosingFee</FeeType>
              <FeeAmount>
                <CurrencyCode>GBP</CurrencyCode>
                <CurrencyAmount>0.0</CurrencyAmount>
              </FeeAmount>
            </FeeComponent>
          </ItemFeeList>
          <ItemFeeAdjustmentList />
          <PromotionList />
          <PromotionAdjustmentList />
        </ShipmentItem>
      </ShipmentItemList>
      <ShipmentItemAdjustmentList />
    </ShipmentEvent>
  </ShipmentEventList>
  <RefundEventList />
  <GuaranteeClaimEventList />
  <ChargebackEventList />
  <PayWithAmazonEventList />
  <ServiceProviderCreditEventList />
  <RetrochargeEventList />
  <RentalTransactionEventList />
  <PerformanceBondRefundEventList />
  <ServiceFeeEventList />
  <DebtRecoveryEventList />
  <LoanServicingEventList />
  <AdjustmentEventList />
</FinancialEvents>
```