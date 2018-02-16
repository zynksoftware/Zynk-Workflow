---
slug: importing-products-to-salesforce-bulk
redirect_from: "/article/296-uploading-products-to-salesforce-bulk"
title: Importing Products to Salesforce (Bulk)
---
This task will update or insert multiple product records and their standard price into Salesforce. Products are matched based on the ProductCode field in Salesforce, and the field from the input file specified in the XML SKU Field setting. If a match is found the existing product will be updated, or if no match is found a new product will be inserted.

## Settings

### Connection 
_Required_  
The Salesforce (Bulk) connection to use, see [Connecting to Salesforce (Bulk)](connecting-to-salesforce-bulk)

### Input File 
_Required_  
The file containing the raw product data to import to Salesforce. The contents of this file will be transformed using the XSLT file provided before being imported to Salesforce.

### Multi-currency
_Required_  
Set to true if your Salesforce organisation has multi-currency enabled. This instructs the task to lookup the corporate currency and treat the prices provided in the input file as this currency.

### XML Price Field
_Optional_  
he XPath query (relative to the one provided in the XPath Query setting) to get the price from a product record in the input file. The value returned by the XPath will be uploaded to the UnitPrice field on product's PriceBookEntry in the standard price book. If this setting is left blank, the task won't update prices in Salesforce.

### XML SKU Field
_Required_  
The XPath query (relative to the one provided in the XPath Query setting) to get the SKU code from a product record in the input file. The value returned by the XPath will be matched to the ProductCode field in Salesforce. If a match is found, the existing product will be updated, otherwise a new record will be created.

### XPath Query
_Required_  
The XPath query to get individual product records from the input file.

### XSLT File
_Optional_  
The XSLT file to use to transform the input file to Product2 objects in the Salesforce XML format. The XML field names outputted from the XSLT must match Salesforce Product2 object API field names. A list of standard API field names can be found [here](http://help.salesforce.com/help/pdfs/en/salesforce_field_names_reference.pdf). Any custom fields added to the Product2 object are supported, and are usually named like `Product_Ref__c`. Note that as the standard price is read directly from the input file based on the XML Price Field setting, it is not required in the output of the XSLT.

## Zynk Settings 
See [Common Task Settings](common-task-settings)

## Examples

You can find an example of how to use this task in the [Salesforce to Sage 50 Integration](salesforce-to-sage-50-integration) article.

Sample input file containing products in the Zynk XML format:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Products>
    <Product>
      <UniqueId>FAX001</UniqueId>
      <Sku>FAX001</Sku>
      <Name>FX010 Plain Paper Fax</Name>
      <Description>FX010 Plain Paper Fax</Description>
      <SalePrice>180</SalePrice>
      <UnitWeight>0</UnitWeight>
      <QtyInStock>0</QtyInStock>
      <QtyOnOrder>0</QtyOnOrder>
      <TaxCode>1</TaxCode>
      <GroupCode>9</GroupCode>
      <Department>1</Department>
      <UnitOfSale>Each</UnitOfSale>
      <NominalCode>4000</NominalCode>
      <Publish>true</Publish>
      <QtyAllocated>0</QtyAllocated>
      <SupplierAccountRef>WAL001</SupplierAccountRef>
      <SupplierDepartment>1</SupplierDepartment>
      <PurchaseNominalCode>5000</PurchaseNominalCode>
      <SupplierPartNo>000006876</SupplierPartNo>
      <Location>Supplied Direct</Location>
    </Product>
  </Products>
</Company>
```

Given this input file, the XPath Query setting would need to be set to `Company/Products/Product`, XML Price Field would be set to `SalePrice` and the XML SKU Field would be set to `Sku`.


Sample XSLT file to convert the input file above to the Salesforce XML format. Note that only fields from the Product2 object can be set:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="xml" version="1.0" encoding="utf-8" indent="yes" xmlns="http://www.force.com/2009/06/asyncapi/dataload"/>
    
  <xsl:template match="/">
    <sObjects xmlns="http://www.force.com/2009/06/asyncapi/dataload">
      <xsl:for-each select="Company/Products/Product">
        <sObject>
          <!-- The task will write out the Product2 Id field when the product already exists in Salesforce, this just needs to be copied by the XSLT -->
          <xsl:if test="Id">
            <Id><xsl:value-of select="Id"/></Id>
          </xsl:if>
          
          <ProductCode><xsl:value-of select="Sku"/></ProductCode>
          <Name><xsl:value-of select="Name"/></Name>
          <Description><xsl:value-of select="Description"/></Description>
          <IsActive><xsl:value-of select="Publish"/></IsActive>
        </sObject>
      </xsl:for-each>
    </sObjects>
  </xsl:template>
</xsl:stylesheet>
```