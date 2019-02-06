---
slug: downloading-orders-from-ekm-powershop
redirect_from: "/article/218-downloading-orders-from-ekm-powershop"
title: Downloading Orders from EKM Powershop
---
This task will download all orders that have been modified since the last data specified, to an XML file.

## Settings
### Connection
_Required_  
The EKM Powershop connection to use.  See the [Connecting to EKM Powershop](connecting-to-ekm-powershop) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all orders, or false to only download new orders since this task last ran.

### Order Details
_Required_  
Set to true to download full details about each order (may be slow if there are many orders to download). Set to false to download only basic information on each order.

### Order Status
_Optional_  
The status of the orders to be downloaded (E.g. Pending). If no value is provided orders of any status will be downloaded.

### Output File
_Required_  
The name of the XML file to export the data to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <soap:Body>
    <GetOrderResponse xmlns="http://publicapi.ekmpowershop.com/">
      <GetOrderResult>
        <Status>Success</Status>
        <Errors />
        <Date>2013-03-27T15:01:35.0544377+00:00</Date>
        <OrderItems>
          <OrderItem>
            <ProductID>97</ProductID>
            <ProductName>Whiteboard Drywipe</ProductName>
            <ProductOptions />
            <ProductCode>WB-DW-01</ProductCode>
            <ProductPrice>3</ProductPrice>
            <ProductDiscount>0</ProductDiscount>
            <ProductDelivery>0</ProductDelivery>
            <ProductQuantity>1</ProductQuantity>
            <ProductRRP>0</ProductRRP>
            <ProductTaxApplicable>true</ProductTaxApplicable>
            <ProductTaxRate>20</ProductTaxRate>
            <ProductURL>http://www.example.com/whiteboard-drywipe.asp</ProductURL>
          </OrderItem>
          <OrderItem>
            <ProductID>62</ProductID>
            <ProductName>Example Product Apple iPod touch 8GB - 4th Generation - 8gb</ProductName>
            <ProductOptions>Gift Wrap this Product: Yes&amp;nbsp;&lt;br /&gt;</ProductOptions>
            <ProductCode />
            <ProductPrice>148.89</ProductPrice>
            <ProductDiscount>0</ProductDiscount>
            <ProductDelivery>0</ProductDelivery>
            <ProductQuantity>1</ProductQuantity>
            <ProductRRP>0</ProductRRP>
            <ProductTaxApplicable>true</ProductTaxApplicable>
            <ProductTaxRate>20</ProductTaxRate>
            <ProductURL>http://www.example.com/ipod-touch.asp</ProductURL>
          </OrderItem>
        </OrderItems>
        <CustomerID>2</CustomerID>
        <OrderGateway>Payment on Delivery</OrderGateway>
        <OrderNumber>4/220812/87</OrderNumber>
        <OrderDate>22/08/2012 09:37:45</OrderDate>
        <OrderDateISO>2012-08-22T09:37:45</OrderDateISO>
        <TotalTax>30.978</TotalTax>
        <TotalDelivery>3</TotalDelivery>
        <DiscountsTotal>0</DiscountsTotal>
        <SubTotal>151.89</SubTotal>
        <TotalCost>185.868</TotalCost>
        <FirstName>John</FirstName>
        <LastName>Smith</LastName>
        <CompanyName>Zynk Software</CompanyName>
        <Address1>6-8 Charlotte Square</Address1>
        <Address2 />
        <Town>Newcastle</Town>
        <County>Tyne &amp; Wear</County>
        <Country>United Kingdom</Country>
        <CountryCode>GB</CountryCode>
        <Postcode>NE1 4XF</Postcode>
        <EmailAddress>support@zynk.com</EmailAddress>
        <Telephone>123456789</Telephone>
        <Fax>123456789</Fax>
        <EnteredShippingAddress>true</EnteredShippingAddress>
        <ShippingFirstName>John</ShippingFirstName>
        <ShippingLastName>Smith</ShippingLastName>
        <ShippingCompanyName>Zynk Software</ShippingCompanyName>
        <ShippingAddress1>6-8 Charlotte Square</ShippingAddress1>
        <ShippingAddress2 />
        <ShippingTown>Newcastle</ShippingTown>
        <ShippingCounty>Tyne &amp; Wear</ShippingCounty>
        <ShippingCountry>United Kingdom</ShippingCountry>
        <ShippingCountryCode>GB</ShippingCountryCode>
        <ShippingPostcode>NE1 4XF</ShippingPostcode>
        <ShippingTelephone>01949851004</ShippingTelephone>
        <DeliveryMethod>Express</DeliveryMethod>
        <Discounts />
        <CustomFields />
        <OrderNotes />
        <InternalNotes></InternalNotes>
        <OrderStatus>Pending</OrderStatus>
        <OrderStatusColour>#000000</OrderStatusColour>
        <TransactionID>4/220812/87</TransactionID>
        <TransactionStatus>SUCCESS : 4/220812/87</TransactionStatus>
        <StockReduced>true</StockReduced>
        <ProductsIncludeTax>false</ProductsIncludeTax>
        <DeliveryIncludesTax>false</DeliveryIncludesTax>
        <TaxRate>20</TaxRate>
        <Currency>GBP</Currency>
        <AbandonedOrder>false</AbandonedOrder>
        <EkmStatus>SUCCESS</EkmStatus>
      </GetOrderResult>
    </GetOrderResponse>
  </soap:Body>
</soap:Envelope>
```
