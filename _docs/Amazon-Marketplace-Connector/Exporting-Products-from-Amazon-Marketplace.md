---
slug: exporting-products-from-amazon-marketplace
title: Exporting Products from Amazon Marketplace
---
This task will export a list of products from Amazon in XML format, based on a list of products to search for.

## Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

### Input File
_Required_  
The file containing the list of products to search for. Products can be searched based on SellerSKU, ASIN, GCID, UPC, EAN, ISBN, or JAN. A sample is provided below.

### Output File
_Required_  
The name of the file to export the downloaded products to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Products>
  <Product Id="B07M7P1SQF" IdType="ASIN" />
  <Product Id="814799025607" IdType="EAN" />
  <Product Id="9781933988665" IdType="ISBN" />
</Products>
```

Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<MatchingProducts>
  <MatchingProduct Id="B07M7P1SQF" IdType="ASIN" Status="Success" MarketplaceId="A1F83G8C2ARO7P" MarketplaceName="Amazon.co.uk">
    <Products>
      <Product xmlns="http://mws.amazonservices.com/schema/Products/2011-10-01">
        <Identifiers>
          <MarketplaceASIN>
            <MarketplaceId>A1F83G8C2ARO7P</MarketplaceId>
            <ASIN>B07M7P1SQF</ASIN>
          </MarketplaceASIN>
        </Identifiers>
        <AttributeSets>
          <ns2:ItemAttributes xml:lang="en-GB" xmlns:ns2="http://mws.amazonservices.com/schema/Products/2011-10-01/default.xsd">
            <ns2:Binding>Misc.</ns2:Binding>
            <ns2:Brand>Artistic Colour Gloss</ns2:Brand>
            <ns2:Label>Artistic Colour Gloss</ns2:Label>
            <ns2:Manufacturer>Artistic Colour Gloss</ns2:Manufacturer>
            <ns2:ProductGroup>Beauty</ns2:ProductGroup>
            <ns2:ProductTypeName>BEAUTY</ns2:ProductTypeName>
            <ns2:Publisher>Artistic Colour Gloss</ns2:Publisher>
            <ns2:SmallImage>
              <ns2:URL>http://ecx.images-amazon.com/images/I/41BeRvC82wL._SL75_.jpg</ns2:URL>
              <ns2:Height Units="pixels">75</ns2:Height>
              <ns2:Width Units="pixels">75</ns2:Width>
            </ns2:SmallImage>
            <ns2:Studio>Artistic Colour Gloss</ns2:Studio>
            <ns2:Title>Crave The Rave 2018 Gel Polish Collection - Dance All Night (2100181) 15ml</ns2:Title>
          </ns2:ItemAttributes>
        </AttributeSets>
        <Relationships />
        <SalesRankings />
      </Product>
    </Products>
  </MatchingProduct>
  <MatchingProduct Id="814799025607" IdType="EAN" Status="ClientError" MarketplaceId="A1F83G8C2ARO7P" MarketplaceName="Amazon.co.uk">
    <Error xmlns="http://mws.amazonservices.com/schema/Products/2011-10-01">
      <Type>Sender</Type>
      <Code>InvalidParameterValue</Code>
      <Message>Invalid EAN identifier 814799025607 for marketplace A1F83G8C2ARO7P</Message>
    </Error>
  </MatchingProduct>
  <MatchingProduct Id="9781933988665" IdType="ISBN" Status="Success" MarketplaceId="A1F83G8C2ARO7P" MarketplaceName="Amazon.co.uk">
    <Products>
      <Product xmlns="http://mws.amazonservices.com/schema/Products/2011-10-01">
        <Identifiers>
          <MarketplaceASIN>
            <MarketplaceId>A1F83G8C2ARO7P</MarketplaceId>
            <ASIN>1933988665</ASIN>
          </MarketplaceASIN>
        </Identifiers>
        <AttributeSets>
          <ns2:ItemAttributes xml:lang="en-GB" xmlns:ns2="http://mws.amazonservices.com/schema/Products/2011-10-01/default.xsd">
            <ns2:Author>Haralambos Marmanis</ns2:Author>
            <ns2:Author>Dmitry Babenko</ns2:Author>
            <ns2:Binding>Paperback</ns2:Binding>
            <ns2:Edition>1</ns2:Edition>
            <ns2:ItemDimensions>
              <ns2:Height Units="inches">9.25</ns2:Height>
              <ns2:Length Units="inches">7.38</ns2:Length>
              <ns2:Width Units="inches">0.73</ns2:Width>
              <ns2:Weight Units="pounds">1.3800937601200</ns2:Weight>
            </ns2:ItemDimensions>
            <ns2:IsAdultProduct>false</ns2:IsAdultProduct>
            <ns2:Label>Manning Publications</ns2:Label>
            <ns2:Languages>
              <ns2:Language>
                <ns2:Name>english</ns2:Name>
                <ns2:Type>Published</ns2:Type>
              </ns2:Language>
              <ns2:Language>
                <ns2:Name>english</ns2:Name>
                <ns2:Type>Original Language</ns2:Type>
              </ns2:Language>
              <ns2:Language>
                <ns2:Name>english</ns2:Name>
                <ns2:Type>Unknown</ns2:Type>
              </ns2:Language>
            </ns2:Languages>
            <ns2:ListPrice>
              <ns2:Amount>28.99</ns2:Amount>
              <ns2:CurrencyCode>GBP</ns2:CurrencyCode>
            </ns2:ListPrice>
            <ns2:Manufacturer>Manning Publications</ns2:Manufacturer>
            <ns2:NumberOfItems>1</ns2:NumberOfItems>
            <ns2:NumberOfPages>368</ns2:NumberOfPages>
            <ns2:PackageDimensions>
              <ns2:Height Units="inches">0.799999999184000</ns2:Height>
              <ns2:Length Units="inches">9.099999990718000</ns2:Length>
              <ns2:Width Units="inches">7.299999992554000</ns2:Width>
              <ns2:Weight Units="pounds">1.35</ns2:Weight>
            </ns2:PackageDimensions>
            <ns2:PackageQuantity>1</ns2:PackageQuantity>
            <ns2:ProductGroup>Book</ns2:ProductGroup>
            <ns2:ProductTypeName>ABIS_BOOK</ns2:ProductTypeName>
            <ns2:PublicationDate>2009-07-08</ns2:PublicationDate>
            <ns2:Publisher>Manning Publications</ns2:Publisher>
            <ns2:ReleaseDate>2009-07-08</ns2:ReleaseDate>
            <ns2:SmallImage>
              <ns2:URL>http://ecx.images-amazon.com/images/I/51EEz05N2HL._SL75_.jpg</ns2:URL>
              <ns2:Height Units="pixels">75</ns2:Height>
              <ns2:Width Units="pixels">60</ns2:Width>
            </ns2:SmallImage>
            <ns2:Studio>Manning Publications</ns2:Studio>
            <ns2:Title>Algorithms of the Intelligent Web</ns2:Title>
          </ns2:ItemAttributes>
        </AttributeSets>
        <Relationships />
        <SalesRankings>
          <SalesRank>
            <ProductCategoryId>book_display_on_website</ProductCategoryId>
            <Rank>1277435</Rank>
          </SalesRank>
          <SalesRank>
            <ProductCategoryId>269709</ProductCategoryId>
            <Rank>831</Rank>
          </SalesRank>
          <SalesRank>
            <ProductCategoryId>269776</ProductCategoryId>
            <Rank>2531</Rank>
          </SalesRank>
          <SalesRank>
            <ProductCategoryId>269834</ProductCategoryId>
            <Rank>4202</Rank>
          </SalesRank>
        </SalesRankings>
      </Product>
    </Products>
  </MatchingProduct>
</MatchingProducts>
```