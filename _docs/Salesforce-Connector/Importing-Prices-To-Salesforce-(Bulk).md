---
slug: importing-prices-to-salesforce-bulk
redirect_from: "/article/724-uploading-prices-to-salesforce-bulk"
title: Importing Prices To Salesforce (Bulk)
---


This task will update or insert multiple pricebook records. Products are matched based on the ProductCode field in Salesforce, and the field from the input file specified in the XML SKU Field setting. Pricebooks are matched based on the Name field in Salesforce, and the field from the input field specified in the XML Pricebook setting. If a matching Pricebook entry is found for the product, the existing pricebook entry will be updated, otherwise a pricebook entry will be inserted.


## Settings

### Connection 
_Required_  
The Salesforce (Bulk) connection to use, see [Connecting to Salesforce (Bulk)](connecting-to-salesforce-bulk)

### Input File 
_Required_  
The file containing the raw product data to import to Salesforce. The contents of this file will be transformed using the XSLT file provided before being imported to Salesforce.

### Multi-currency
_Required_  
Set to true if your Salesforce organisation has multi-currency enabled.

### XML Currency Field
_Dependant_  
The XPath query (relative to the one provided in the XPath Query setting) to get the currency from a price in the input file. The currency should be provided as a 3 letter ISO currency code (e.g. GBP, EUR, USD). This setting is only required when the Multi-currency setting is set to true.

### XML Pricebook Field
_Required_  
The XPath query (relative to the one provided in the XPath Query setting) to get the pricebook name from a price in the input file. The value returned by the XPath will be matched to the Pricebook.Name field  in Salesforce. If no match is found, the price will not be imported.

### XML SKU Field
_Required_  
The XPath query (relative to the one provided in the XPath Query setting) to get the SKU code from a product record in the input file. The value returned by the XPath will be matched to the Product2.ProductCode field in Salesforce. If no match is found, the price will not be imported.

### XPath Query
_Required_  
The XPath query to get individual price records from the input file.

### XSLT File
_Required_  
The XSLT file to use to transform the input file to PricebookEntry objects in the Salesforce XML format. The XML field names outputted from the XSLT must match Salesforce PricebookEntry object API field names. A list of standard API field names can be found [here](http://help.salesforce.com/help/pdfs/en/salesforce_field_names_reference.pdf). Any custom fields added to the PricebookEntry object are supported, and are usually named like `Price_Ref__c`. Note that the Id, Pricebook2Id and Product2Id are determined by the task, but do still need to be copied by the XSLT, see the sample XSLT below for more an example.

### Zynk Settings 
See [Common Task Settings](common-task-settings)


## Examples

Sample input file containing prices in the Zynk XML format:

```xml
<?xml version="1.0" encoding="utf-8"?>
    <Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <PriceLists>
        <PriceList AllRecords="false">
          <UniqueId>1008</UniqueId>
          <Name>Standard Price Book</Name>
          <Reference>Standard</Reference>
          <Currency>GBP</Currency>
          <Type>PriceList</Type>
          <Prices>
            <Price Action="Upsert">
              <UniqueId>6689</UniqueId>
              <DiscountType>Fixed</DiscountType>
              <StockCode>TEST</StockCode>
              <StoredPrice>34.2</StoredPrice>
              <Value>0</Value>
              <ExternalReference>PROD001</ExternalReference>
              <BaseQty xsi:nil="true" />
              <QtyBreak xsi:nil="true" />
              <DiscountAmountValue xsi:nil="true" />
              <DiscountPercentValue xsi:nil="true" />
            </Price>
          </Prices>
        </PriceList>
        <PriceList AllRecords="false">
          <UniqueId>1009</UniqueId>
          <Name>Euro Prices</Name>
          <Reference>Euro</Reference>
          <Currency>EUR</Currency>
          <Type>PriceList</Type>
          <Prices>
            <Price Action="Upsert">
              <UniqueId>7021</UniqueId>
              <DiscountType>Fixed</DiscountType>
              <StockCode>TEST</StockCode>
              <StoredPrice>25.2</StoredPrice>
              <Value>0</Value>
              <ExternalReference>PROD001</ExternalReference>
              <BaseQty xsi:nil="true" />
              <QtyBreak xsi:nil="true" />
              <DiscountAmountValue xsi:nil="true" />
              <DiscountPercentValue xsi:nil="true" />
            </Price>
          </Prices>
        </PriceList>
      </PriceLists>
    </Company>
```

Given this input file, the task's settings will need to be set as follows:

- XPath Query - `Company/PriceLists/PriceList/Prices/Price`
- XML Currency Field - `../../Currency`
- XML Pricebook Field  - `../../Name`
- XML SKU Field - `StockCode`


Sample XSLT file to convert the input file above to the Salesforce XML format. Note that only fields from the PricebookEntry object can be set:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="xml" version="1.0" encoding="utf-8" indent="yes" xmlns="http://www.force.com/2009/06/asyncapi/dataload"/>
    
  <xsl:template match="/">
    <sObjects xmlns="http://www.force.com/2009/06/asyncapi/dataload">
      <xsl:for-each select="Company/PriceLists/PriceList/Prices/Price">
        <sObject>
          <xsl:choose>
            <!-- The task will write out the PricebookEntry Id field when the price already exists in Salesforce, this just needs to be copied by the XSLT -->
            <xsl:when test="Id"> 
              <Id><xsl:value-of select="Id"/></Id>
            </xsl:when>
    
            <!-- The task will write out the PricebookEntry Pricebook2Id and Product2Id fields if a new price needs to be created in Salesforce, they just need to be copied by the XSLT -->
            <xsl:otherwise>
              <Pricebook2Id><xsl:value-of select="Pricebook2Id"/></Pricebook2Id>
              <Product2Id><xsl:value-of select="Product2Id"/></Product2Id>
              <CurrencyIsoCode><xsl:value-of select="../../Currency" /></CurrencyIsoCode>
            </xsl:otherwise>
          </xsl:choose>
     
            <UnitPrice><xsl:value-of select="StoredPrice"/></UnitPrice>
          <UseStandardPrice>false</UseStandardPrice>
          <IsActive>true</IsActive>
        </sObject>
      </xsl:for-each>
    </sObjects>
  </xsl:template>
</xsl:stylesheet>
```
