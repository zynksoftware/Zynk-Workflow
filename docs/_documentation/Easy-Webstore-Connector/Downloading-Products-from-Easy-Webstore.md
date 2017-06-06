---
slug: downloading-products-from-easy-webstore
redirect_from: "/article/207-downloading-products-from-easy-webstore"
title: Downloading Products from Easy Webstore
---
This task will download products from your store to an XML file.

## Settings
### Connection
_Required_  
The Easy Webstore connection to use.  See the [Connecting to Easy Webstore](connecting-to-easy-webstore) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The XML file to save the results to.

### Product ID
_Optional_  
Specify a product ID to download a particular product. Leave blank to download all products.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfProduct xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <ExtensionData />
    <ID>1962364</ID>
    <Body>The Olympus SP-600UZ is a 12 megapixel digital camera with a 15x zoom
lens. The lens has wide angle capabilities. The combination of the
longer lens and the ability to squeeze in wide scenes gives the camera a
great deal of flexibility.  As you would expect with that length of
lens image stabilisation has been built into the SP-600UZ by Olympus.
Other key features include the ability to capture High Definition
movies.  <br />
<br />
Some more advanced features such as bracketing and a choice of metering
types are available, but the SP-600UZ does not have manual exposure
modes. <br />
<br />
</Body>
    <DateAdded>1970-01-01T00:00:00</DateAdded>
    <FeaturedItem>true</FeaturedItem>
    <MetaDescription />
    <MetaKeywords />
    <PrimaryCategoryID>0</PrimaryCategoryID>
    <SearchEngineSpecificTitle />
    <Teaser>The Olympus SP-600UZ is a new 12-megapixel camera with a 15x zoom lens
that spans a 35mm equivalent focal range of 28-420mm. Featuring a 2.7
LCD screen, mechanical image stabilisation, HD movie recording, Magic
Filters, Beauty Mode, in-camera panorama stitching, Advanced Face
Detection and Shadow Adjustment Technology.
</Teaser>
    <TeaserDisplayOption>Let_System_Decide</TeaserDisplayOption>
    <Title>Olympus SP-600UZ</Title>
    <URL>Olympus-SP-600UZ_A16264.aspx</URL>
    <Adult>false</Adult>
    <Brand />
    <Colour />
    <Condition>New</Condition>
    <GTIN />
    <HasProductOptions>false</HasProductOptions>
    <Manufacturer />
    <ManufacturersPartNumber />
    <MinimumOrderQuantity>0</MinimumOrderQuantity>
    <Price>3000</Price>
    <ProductCode>PROD001</ProductCode>
    <RRPPrice>0</RRPPrice>
    <RelatedProducts />
    <SalesTaxID>0</SalesTaxID>
    <ShippingAmountOrWeight>0</ShippingAmountOrWeight>
    <ShowAddToCartQuantities>true</ShowAddToCartQuantities>
    <SimpleOptions />
    <Size />
    <Specifications />
    <StockLevel>19</StockLevel>
    <StockMessage />
    <TieredPricing />
  </Product>
  <Product>
    <ExtensionData />
    <ID>1962374</ID>
    <Body>The camera is targeted at beginners looking for convenience and easy
operation, and it delivers those. However, its photo quality is merely
OK, which is to be expected at its price, and its performance is far
from snappy (also expected). The camera isn't totally without value,
though, and depending on the end use of your photos, its results may be
satisfactory for your needs thanks to some excellent color quality. Available in three colors--black, silver, and orange--the S2100 is
certainly one of the more attractive budget-friendly cameras I've seen
and feels well-constructed for its price.
</Body>
    <DateAdded>1970-01-01T00:00:00</DateAdded>
    <FeaturedItem>false</FeaturedItem>
    <MetaDescription />
    <MetaKeywords />
    <PrimaryCategoryID>276753</PrimaryCategoryID>
    <SearchEngineSpecificTitle />
    <Teaser>The Sony Cyber-shot DSC-S2100 is the company's entry-level compact
camera. It's currently the only model in Sony's 2010 lineup to feature
AA-size batteries. That is really its key selling point other than a
larger-than-typical LCD.
</Teaser>
    <TeaserDisplayOption>Let_System_Decide</TeaserDisplayOption>
    <Title>Sony S2100</Title>
    <URL>Sony-S2100_A1626E.aspx</URL>
    <Adult>false</Adult>
    <Brand />
    <Colour />
    <Condition>New</Condition>
    <GTIN />
    <HasProductOptions>false</HasProductOptions>
    <Manufacturer />
    <ManufacturersPartNumber />
    <MinimumOrderQuantity>0</MinimumOrderQuantity>
    <Price>17440</Price>
    <ProductCode>PROD002</ProductCode>
    <RRPPrice>0</RRPPrice>
    <RelatedProducts />
    <SalesTaxID>0</SalesTaxID>
    <ShippingAmountOrWeight>0</ShippingAmountOrWeight>
    <ShowAddToCartQuantities>true</ShowAddToCartQuantities>
    <SimpleOptions />
    <Size />
    <Specifications />
    <StockLevel>888</StockLevel>
    <StockMessage />
    <TieredPricing />
  </Product>
</ArrayOfProduct>
```