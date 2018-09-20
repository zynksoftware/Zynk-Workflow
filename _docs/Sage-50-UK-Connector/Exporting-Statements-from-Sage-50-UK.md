---
slug: exporting-statements-from-sage-50-uk
redirect_from: "/article/403-exporting-statements-from-sage-50-uk"
title: Exporting Statements from Sage 50 UK
---
This task will export statements from Sage 50 to Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.

### Query Settings
_Optional_  

 * **Columns** - Allows you to specify additional columns to include in the export.  Additional fields will be exported in the CustomFields section in the XML.  Be sure to include the table name for each of the additional columns provided eg. `[STOCK].[QTY_LAST_STOCK_TAKE]`.  If the table that the column you are trying to retrieve is not used by the standard export, you will need to add the table to Joins.
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported.

### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The name of the file to export to. Data is exported in Zynk XML format

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


Sample output file:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Statements>
    <Statement>
      <AccountReference>ABS001</AccountReference>
      <Date>2013-10-25T14:41:44.476383+01:00</Date>
      <InvoiceAddress>
        <Title />
        <Forename>Mike</Forename>
        <Surname>Hall</Surname>
        <Company>ABS Garages Ltd</Company>
        <Description>Mike Hall - NE31 1VB</Description>
        <Address1>Unit 34</Address1>
        <Address2>Holystone Ind Estate</Address2>
        <Town>Hebburn</Town>
        <Postcode>NE31 1VB</Postcode>
        <County>Tyne & Wear</County>
        <Telephone>0191 254 5909</Telephone>
        <Fax>0191 254 5907</Fax>
        <Mobile>0191 254 5908</Mobile>
        <Email>newbusinessadvice@sage.com</Email>
        <Website>www.sage.co.uk</Website>
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <TradeContact>Peter Yates</TradeContact>
        <Activities />
        <Groups />
      </InvoiceAddress>
      <Balance>2533.31</Balance>
      <CreditLimit>4000</CreditLimit>
      <Transactions>
        <Transaction>
          <Id>1010</Id>
          <TransactionType>SalesInvoice</TransactionType>
          <AccountReference>ABS001</AccountReference>
          <TransactionDate>2009-04-24T00:00:00</TransactionDate>
          <PostedDate>2009-04-24T00:00:00</PostedDate>
          <Reference>58</Reference>
          <PaymentReference>1010</PaymentReference>
          <Details>A4 Carbon Copy Book - Triplicate</Details>
          <NetAmount>2110.55</NetAmount>
          <TaxRate xsi:nil="true" />
          <TaxCode xsi:nil="true" />
          <TaxAmount>422.76</TaxAmount>
          <ElectronicTransaction>false</ElectronicTransaction>
          <OutstandingAmount>2533.31</OutstandingAmount>
          <TransactionNumber>1010</TransactionNumber>
          <BankReference />
          <Discount xsi:nil="true" />
          <ExchangeRate>1</ExchangeRate>
          <VatInclusive>false</VatInclusive>
          <CustomFields />
        </Transaction>
      </Transactions>
    </Statement>
  </Statements>
</Company>
```