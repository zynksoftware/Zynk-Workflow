---
slug: importing-records-to-salesforce-bulk
redirect_from: "/article/297-uploading-records-to-salesforce-bulk"
title: Importing Records to Salesforce (Bulk)
---
This task will update or insert multiple records in Salesforce. Existing records are matched with those provided in the input file, based on the Salesforce field specified in the Salesforce Key Field setting, and the field from the input file specified by the XML Key Field setting. Unlike the [Importing Records to Salesforce](importing-records-to-salesforce) and [Bulk Salesforce Operation](bulk-salesforce-operation) task, the Salesforce field does not need to be of type External Id. If a match is found the existing record will be updated, or if no match is found a new record will be inserted.


## Settings

### Connection 
_Required_  
The Salesforce (Bulk) connection to use, see [Connecting to Salesforce (Bulk)](connecting-to-salesforce-bulk)

### Salesforce Key Field
_Required_  
The field in Salesforce to use to match existing records.

### Salesforce Object 
_Required_  
The record type to upload e.g. Account.

### Input File
_Required_  
The file containing the raw product data to import to Salesforce. The contents of this file will be transformed using the XSLT file provided before being imported to Salesforce.

### XML Key Field 
_Required_  
The relative XPath query to get the value to match on from a record in the input file.

### XPath Query 
_Required_  
The XPath query (relative to the one provided in the XPath Query setting) to get individual records from the input file.

### XSLT File
_Required_  
The XSLT file to use to transform the input file to objects in the Salesforce XML format. The XML field names outputted from the XSLT must match Salesforce object API field names. A list of standard API field names can be found [here](http://help.salesforce.com/help/pdfs/en/salesforce_field_names_reference.pdf). Any custom fields added to the chosen object are supported, and are usually named like `Account_Ref__c`.

### Zynk Settings 
See [Common Task Settings](common-task-settings)

## Examples

You can find an example of how to use this task in the [Salesforce to Sage 50 Integration](salesforce-to-sage-50-integration) article.

Sample input file containing customers in the Zynk XML format, to be uploaded to Salesforce as accounts:

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <UniqueId>ABS001</UniqueId>
      <AccountReference>ABS001</AccountReference>
      <CompanyName>ABS Garages Ltd</CompanyName>
      <Balance>2533.31</Balance>
      <Currency>GBP</Currency>
      <CustomerInvoiceAddress>
        <Forename>Mike</Forename>
        <Surname>Hall</Surname>
        <Company>ABS Garages Ltd</Company>
        <Address1>Unit 34</Address1>
        <Address2>Holystone Ind Estate</Address2>
        <Town>Hebburn</Town>
        <Postcode>NE31 1VB</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <Telephone>0191 254 5909</Telephone>
        <Fax>0191 254 5907</Fax>
        <Email>newbusinessadvice@sage.com</Email>
        <Website>www.sage.co.uk</Website>
      </CustomerInvoiceAddress>
    </Customer>
  </Customers>
</Company>
```

Given this input file, the XPath Query setting would need to be set to `Company/Customers/Customer`, the XML Key Field would be set to `AccountReference` and the Salesforce Object would be set to `Account`. The Salesforce Key Field setting would be set to `AccountNumber`, as this is the field which will be used when searching for existing accounts in Salesforce.

Sample XSLT file to convert the input file above to the Salesforce XML format:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="xml" version="1.0" encoding="utf-8" indent="yes" xmlns="http://www.force.com/2009/06/asyncapi/dataload"/>
  
  <xsl:template match="/">
    <sObjects xmlns="http://www.force.com/2009/06/asyncapi/dataload">
      <xsl:for-each select="Company/Customers/Customer">
        <sObject>
          <!-- The task will write out the Id field when the record already exists in Salesforce, this just needs to be copied by the XSLT -->
          <xsl:if test="Id"> 
            <Id><xsl:value-of select="Id"/></Id>
          </xsl:if>
    				
          <AccountNumber>
            <xsl:value-of select="AccountReference"/>
          </AccountNumber>
          <CurrencyIsoCode>
            <xsl:value-of select="Currency" />
          </CurrencyIsoCode>
          <Name>
            <xsl:value-of select="CompanyName" />
          </Name>
          <BillingStreet>
            <xsl:value-of select="CustomerInvoiceAddress/Address1"/>
            <xsl:text> </xsl:text>
            <xsl:value-of select="CustomerInvoiceAddress/Address2"/>
          </BillingStreet>
          <BillingCity>
            <xsl:value-of select="CustomerInvoiceAddress/Town" />
          </BillingCity>
          <BillingState>
            <xsl:value-of select="CustomerInvoiceAddress/County" />
          </BillingState>
          <BillingPostalCode>
            <xsl:value-of select="CustomerInvoiceAddress/Postcode" />
          </BillingPostalCode>
          <BillingCountry>
            <xsl:value-of select="CustomerInvoiceAddress/Country" />
          </BillingCountry>
          <Phone>
            <xsl:value-of select="CustomerInvoiceAddress/Telephone" />
          </Phone>
          <Fax>
            <xsl:value-of select="CustomerInvoiceAddress/Fax" />
          </Fax>
          <Website>
            <xsl:value-of select="CustomerInvoiceAddress/Website" />
          </Website>
        </sObject>
      </xsl:for-each>
    </sObjects>
  </xsl:template>
</xsl:stylesheet>
```