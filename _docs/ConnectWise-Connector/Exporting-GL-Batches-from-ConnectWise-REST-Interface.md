---
slug: exporting-gl-batches-from-connectwise-rest-interface
title: Exporting GL Batches from ConnectWise REST Interface
---
This task will retrieve Unposted Invoices, Unposted Expenses and/or Unposted Procurement data from the Accounting Interface in ConnectWise. This task is typically used for integrations with accounting systems, as the data provided from ConnectWise includes the general ledger account numbers associated with the transactions.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Export Unposted Expenses
_Required_  
Specify whether Unposted Expenses should be included in the data. This will be defaulted to False.

### Export Unposted Invoices
_Required_  
Specify whether Unposted Procurement should be included in the data. This will be defaulted to True.

### Export Unposted Procurement
_Required_  
Specify whether Unposted Procurement should be included in the data. This will be defaulted to False.

### Output File
_Required_  
The name of the file to export the GL batch to.

### Owner Level
_Optional_  
Filter to restrict the records that are returned based on Location (Level 2 of the Corporate Structure). You can must specify the Location ID.

### References To Fetch
_Optional_  
The exported data may include fields which reference other records in ConnectWise. If you specify the reference field names here, and the task will fetch the related records and include them in the exported data. The supported fields are listed below: 

* vendor/member
* vendor/vendor
* vendor/company
* vendor/billingTerms
* vendor/site
* vendor/taxCode
* customer/company
* customer/companyType
* customer/contact
* customer/site
* customer/billingTerms
* customer/taxCode
* customer/currency
* transaction/company
* transaction/companyType
* transaction/site
* transaction/billingTerms
* transaction/purchaseOrder
* transaction/project
* transaction/currency
* transaction/taxCode
* transaction/shipToCompany
* transaction/shipCompanyType
* transaction/shipSite
* transaction/shipContact
* expense/member
* expense/company
* expense/project
* expense/currency
* expenseBill/member
* expenseBill/currency
* expenseBill/detailItem/company
* expenseBill/detailItem/expenseClass
* expenseBill/detailItem/currency
* purchaseTransaction/company
* purchaseTransaction/companyType
* purchaseTransaction/contact
* purchaseTransaction/site
* purchaseTransaction/currency
* purchaseTransaction/billingTerms
* purchaseTransaction/shipToCompany
* purchaseTransaction/shipToCompanyType
* purchaseTransaction/shipToContact
* purchaseTransaction/shipToSite
* purchaseTransaction/taxCode
* purchaseTransaction/purchaseDetailItem/item
* purchaseTransaction/purchaseDetailItem/shipmentMethod
* purchaseTransaction/purchaseDetailTaxItem/warehouseBin
* adjustmentTransaction/adjustmentDetailItem/item
* inventoryTransfer/item
* inventoryTransfer/currency
* inventoryTransfer/shipmentMethod
* inventoryTransfer/bin
* inventoryTransfer/warehouse
* inventoryTransfer/transferFromBin
* inventoryTransfer/transferToBin
* inventoryTransfer/taxCode

### Thru Date
_Optional_  
Filter to restrict the records that are returned based on the date they were taken.	If no value is specified the default used by ConnectWise is the current date.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample Unposted Invoices data:

```
<?xml version="1.0" encoding="utf-8"?>
<GLExport xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <company>
        <id>8</id>
        <identifier>Angry Fox, Co.</identifier>
      </company>
      <companyType>
        <id>1</id>
        <name>Customer</name>
      </companyType>
      <contact>
        <id>20</id>
        <name>Robert Storts</name>
      </contact>
      <site>
        <id>7</id>
        <name>Main</name>
      </site>
      <accountNumber>ANGRYF01</accountNumber>
      <billingTerms>
        <id>2</id>
        <name>Net 10</name>
      </billingTerms>
      <billingTermsXref>Net 10</billingTermsXref>
      <dueDays>10</dueDays>
      <taxable>true</taxable>
      <taxCode>
        <id>11</id>
        <name>T1</name>
      </taxCode>
      <stateTaxXref>T1</stateTaxXref>
      <countyTaxXref />
      <cityTaxXref />
      <countryTaxXref />
      <compositeTaxXref />
      <stateTaxRate>20</stateTaxRate>
      <countyTaxRate>0</countyTaxRate>
      <cityTaxRate>0</cityTaxRate>
      <countryTaxRate>0</countryTaxRate>
      <compositeTaxRate>0</compositeTaxRate>
      <taxGroupRate xsi:nil="true" />
      <taxAgencyXref>ANGRYF01</taxAgencyXref>
      <stateTaxAgencyXref>ANGRYF01</stateTaxAgencyXref>
      <countyTaxAgencyXref />
      <cityTaxAgencyXref />
      <countryTaxAgencyXref />
      <compositeTaxAgencyXref />
    </customer>
  </customers>
  <transactions>
    <transaction>
      <id>125</id>
      <glClass />
      <glTypeId>AR</glTypeId>
      <documentDate>2011-06-20T00:00:00</documentDate>
      <documentNumber>119</documentNumber>
      <documentType>INVOICE</documentType>
      <memo />
      <description>Accounts Receivable</description>
      <attention>Robert Storts</attention>
      <salesTerritory>Arnie's Accounts</salesTerritory>
      <company>
        <id>8</id>
        <identifier>Angry Fox, Co.</identifier>
      </company>
      <companyType>
        <id>1</id>
        <name>Customer</name>
      </companyType>
      <companyAccountNumber>ANGRYF01</companyAccountNumber>
      <billingTerms>
        <id>2</id>
        <name>Net 10</name>
      </billingTerms>
      <billingTermsXref>Net 10</billingTermsXref>
      <dueDays>10</dueDays>
      <dueDate>2011-06-30T00:00:00</dueDate>
      <emailDeliveryFlag>false</emailDeliveryFlag>
      <printDeliveryFlag>false</printDeliveryFlag>
      <agreementPrePaymentFlag>false</agreementPrePaymentFlag>
      <accountNumber>9999</accountNumber>
      <billingType>Miscellaneous</billingType>
      <glEntryIds>1010,1011,1012,1013,1014,1015</glEntryIds>
      <total>10</total>
      <taxable>false</taxable>
      <taxableTotal>0</taxableTotal>
      <taxGroupRate>0.2</taxGroupRate>
      <piggyBackFlag>false</piggyBackFlag>
      <taxAccountNumber>9999</taxAccountNumber>
      <salesTax>0</salesTax>
      <stateTax>0</stateTax>
      <countyTax>0</countyTax>
      <cityTax xsi:nil="true" />
      <taxableAmount1>0</taxableAmount1>
      <taxableAmount2>0</taxableAmount2>
      <taxableAmount3>0</taxableAmount3>
      <taxableAmount4>0</taxableAmount4>
      <taxableAmount5>0</taxableAmount5>
      <taxAgencyXref>ANGRYF01</taxAgencyXref>
      <stateTaxXref>T1</stateTaxXref>
      <countyTaxXref />
      <taxId />
      <taxDpAppliedFlag>false</taxDpAppliedFlag>
      <useAvalaraFlag>false</useAvalaraFlag>
      <sendAvalaraTaxFlag>false</sendAvalaraTaxFlag>
      <shipCompanyAccountNumber>ANGRYF01</shipCompanyAccountNumber>
      <shipCompanyType>
        <id>1</id>
        <name>Customer</name>
      </shipCompanyType>
      <shipTaxId />
      <detail>
        <detailItem>
          <id>1009</id>
          <documentDate>2011-06-20T00:00:00</documentDate>
          <documentType>INVOICE</documentType>
          <accountNumber>4000</accountNumber>
          <glClass />
          <glTypeId>RP</glTypeId>
          <glItemId />
          <invoiceSummaryOption>0</invoiceSummaryOption>
          <cost>0</cost>
          <salesCode>0000</salesCode>
          <memo>ghyigui</memo>
          <description>Non-Taxable Products</description>
          <quantity>-1</quantity>
          <total>-10</total>
          <costAccountNumber>0000</costAccountNumber>
          <inventoryAccountNumber>0000</inventoryAccountNumber>
          <productAccountNumber>4000</productAccountNumber>
          <taxCodeXref>T9</taxCodeXref>
          <taxAgencyXref />
          <taxNote />
          <taxRate>0</taxRate>
          <taxRatePercent>0</taxRatePercent>
          <taxableFlag>false</taxableFlag>
          <taxable2Flag>false</taxable2Flag>
          <taxable3Flag>false</taxable3Flag>
          <taxable4Flag>false</taxable4Flag>
          <taxable5Flag>false</taxable5Flag>
          <itemTaxableFlag>false</itemTaxableFlag>
          <itemPrice>10</itemPrice>
          <itemCost>0</itemCost>
          <itemDescription>tewst</itemDescription>
          <salesDescription>ghyigui</salesDescription>
          <unitOfMeasure>
            <id>2</id>
            <name>Hour</name>
          </unitOfMeasure>
          <serializedFlag>false</serializedFlag>
          <serialNumbers />
          <dropShippedFlag>true</dropShippedFlag>
          <itemTypeXref>Service</itemTypeXref>
          <inventoryXref>0000</inventoryXref>
          <cogsXref>0000</cogsXref>
          <uomScheduleXref />
          <locationXref>DEFAULT</locationXref>
        </detailItem>
        <detailItem>
          <id>1016</id>
          <documentDate>2011-06-20T00:00:00</documentDate>
          <documentType>INVOICE</documentType>
          <accountNumber>9999</accountNumber>
          <glClass />
          <glTypeId>ST</glTypeId>
          <glItemId />
          <invoiceSummaryOption>0</invoiceSummaryOption>
          <cost>0</cost>
          <salesCode />
          <memo>Sales Tax</memo>
          <description>Level 1 Sales Tax</description>
          <quantity>0</quantity>
          <total>0</total>
          <costAccountNumber />
          <inventoryAccountNumber />
          <productAccountNumber>4000</productAccountNumber>
          <taxCodeXref>T9</taxCodeXref>
          <taxAgencyXref />
          <taxNote>AUTOSTAX</taxNote>
          <taxRate>0.2</taxRate>
          <taxRatePercent>20</taxRatePercent>
          <taxableFlag>false</taxableFlag>
          <taxable2Flag>false</taxable2Flag>
          <taxable3Flag>false</taxable3Flag>
          <taxable4Flag>false</taxable4Flag>
          <taxable5Flag>false</taxable5Flag>
          <itemTaxableFlag>false</itemTaxableFlag>
          <itemPrice>0</itemPrice>
          <itemCost>0</itemCost>
          <itemDescription />
          <salesDescription />
          <unitOfMeasure>
            <id>2</id>
            <name>Hour</name>
          </unitOfMeasure>
          <serializedFlag>false</serializedFlag>
          <serialNumbers />
          <dropShippedFlag>false</dropShippedFlag>
          <itemTypeXref />
          <inventoryXref />
          <cogsXref />
          <uomScheduleXref />
          <locationXref>DEFAULT</locationXref>
        </detailItem>
      </detail>
    </transaction>
  </transactions>
</GLExport>
```

Sample Unposted Procurement data:

```
<?xml version="1.0" encoding="utf-8"?>
<GLExport xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <vendors>
    <vendor>
      <vendor>
        <id>6</id>
        <identifier>Blue Light, Co.</identifier>
      </vendor>
      <vendorNumber />
      <company>
        <id>6</id>
        <identifier>Blue Light, Co.</identifier>
      </company>
      <accountNumber>Blue Light Co</accountNumber>
      <billingTerms>
        <id>2</id>
        <name>Net 10</name>
      </billingTerms>
      <dueDays>10</dueDays>
      <site>
        <id>5</id>
        <name>Main</name>
      </site>
      <taxCode>
        <id>11</id>
        <name>Standard VAT</name>
      </taxCode>
    </vendor>
    <vendor>
      <vendor>
        <id>3</id>
        <identifier>CONNECTWISE</identifier>
      </vendor>
      <vendorNumber />
      <company>
        <id>3</id>
        <identifier>CONNECTWISE</identifier>
      </company>
      <accountNumber />
      <billingTerms>
        <id>2</id>
        <name>Net 10</name>
      </billingTerms>
      <dueDays>10</dueDays>
      <site>
        <id>2</id>
        <name>Main</name>
      </site>
      <taxCode>
        <id>11</id>
        <name>Standard VAT</name>
      </taxCode>
    </vendor>
  </vendors>
  <purchaseTransactions>
    <purchaseTransaction>
      <id>PO #COMPANYBPO, Packing Slip: COMPANYBPO</id>
      <documentDate>2014-05-01T00:00:00</documentDate>
      <documentNumber>COMPANYBPO</documentNumber>
      <description>Purchase</description>
      <memo />
      <apAccountNumber>9000</apAccountNumber>
      <purchaseDate>2014-05-01T00:00:00</purchaseDate>
      <company>
        <id>3</id>
        <identifier>CONNECTWISE</identifier>
      </company>
      <contact>
        <id>2</id>
        <name>Arnie Bellini</name>
      </contact>
      <site>
        <id>2</id>
        <name>Main</name>
      </site>
      <purchaseClass />
      <freightAmount>0</freightAmount>
      <freightPackingSlip>COMPANYBPO</freightPackingSlip>
      <packingSlip>COMPANYBPO</packingSlip>
      <dropshipFlag>true</dropshipFlag>
      <total>12.5</total>
      <billingTerms>
        <id>2</id>
        <name>Net 10</name>
      </billingTerms>
      <billingTermsXref>Net 10</billingTermsXref>
      <dueDays>10</dueDays>
      <vendorNumber />
      <vendorAccountNumber />
      <vendorInvoiceDate>2014-05-01T00:00:00</vendorInvoiceDate>
      <vendorInvoiceNumber>COMPANYBINV</vendorInvoiceNumber>
      <taxAgencyXref />
      <stateTaxXref>T1</stateTaxXref>
      <countyTaxXref />
      <cityTaxXref />
      <shipToCompany>
        <id>134</id>
        <identifier>Zynk Software Limited GBP</identifier>
      </shipToCompany>
      <shipToCompanyAccountNumber>ZYNK0001</shipToCompanyAccountNumber>
      <shipToCompanyType>
        <id>6</id>
        <name>Vendor</name>
      </shipToCompanyType>
      <shipToContact>
        <id>179</id>
        <name>Chris Hotchkiss</name>
      </shipToContact>
      <shipToSite>
        <id>136</id>
        <name>Main</name>
      </shipToSite>
      <taxGroupRate>0.2</taxGroupRate>
      <useAvalaraTaxFlag>false</useAvalaraTaxFlag>
      <purchaseHeaderTaxGroup>Standard VAT</purchaseHeaderTaxGroup>
      <purchaseHeaderTaxableFlag>false</purchaseHeaderTaxableFlag>
      <purchaseHeaderFreightTaxableFlag>false</purchaseHeaderFreightTaxableFlag>
      <purchaseDetail>
        <purchaseDetailItem>
          <id>1299</id>
          <documentDate>5/1/2014 5:21:58 AM</documentDate>
          <glClass />
          <glTypeId>RP</glTypeId>
          <glItemId>PATCH10</glItemId>
          <salesCode>1111</salesCode>
          <description>Purchase</description>
          <cost>12.5</cost>
          <memo>10ft Patch Cable</memo>
          <taxNote />
          <vendorNumber />
          <accountNumber>4001</accountNumber>
          <costAccountNumber>1111</costAccountNumber>
          <inventoryAccountNumber>1111</inventoryAccountNumber>
          <vendorAccountNumber />
          <item>
            <id>743</id>
            <identifier>PATCH10</identifier>
          </item>
          <itemDescription>10ft Patch Cable</itemDescription>
          <salesDescription>10ft Patch Cat5E Cable</salesDescription>
          <taxable>true</taxable>
          <itemPrice>7</itemPrice>
          <itemCost>0.25</itemCost>
          <unitOfMeasure>
            <id>13</id>
            <name>Each</name>
          </unitOfMeasure>
          <quantity>-50</quantity>
          <total>-12.5</total>
          <serializedFlag>false</serializedFlag>
          <serialNumbers />
          <dropShippedFlag>true</dropShippedFlag>
          <lineNumber>1</lineNumber>
          <subCategory>
            <id>24</id>
            <name>Miscellaneous</name>
          </subCategory>
          <shipmentMethod>
            <id>9</id>
            <name>USPS Priority</name>
          </shipmentMethod>
          <itemTypeXref>Other Charge</itemTypeXref>
          <inventoryXref>1111</inventoryXref>
          <cogsXref>1111</cogsXref>
          <uomScheduleXref>DEFAULT</uomScheduleXref>
          <priceLevelXref>DEFAULT</priceLevelXref>
          <locationXref>DEFAULT</locationXref>
          <purchaseHeaderTaxGroup>Standard VAT</purchaseHeaderTaxGroup>
          <taxCodeXref />
          <taxRate>0</taxRate>
          <taxAgencyXref />
        </purchaseDetailItem>
      </purchaseDetail>
      <purchaseDetailTax />
    </purchaseTransaction>
  </purchaseTransactions>
</GLExport>
```