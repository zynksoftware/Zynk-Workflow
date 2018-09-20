---
slug: exporting-customers-from-sage-50-uk
redirect_from: "/article/395-exporting-customers-from-sage-50-uk"
title: Exporting Customers from Sage 50 UK
---
This task will export customer information from Sage 50 sales ledger to [Sage 50 UK Customer XML](sage-50-uk-customer-xml).

## Settings  
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Attachment Search Pattern
_Required_  
File search pattern for attachment export e.g. *.PDF

### Export Attachments
_Required_  
Set to True if you want the attachments exported from Customers note: this will result in very large XML output files.

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
The name of the file to export to. Data is exported in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples  
Sample output file, for full documentation and samples see [Sage 50 UK Customer XML](sage-50-uk-customer-xml): 

```xml 
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <Customers>
        <Customer>
            <UniqueId>ABS001</UniqueId>
            <AccountReference>ABS001</AccountReference>
            <CompanyName>ABS Garages Ltd</CompanyName>
            <Balance>2533.31</Balance>
            <VatNumber>GB745 4584 68</VatNumber>
            <SendElectronicInvoice xsi:nil="true" />
            <SendElectronicLetter>false</SendElectronicLetter>
            <CustomerInvoiceAddress>
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
                <Country>CH</Country>
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
            </CustomerInvoiceAddress>
            <CustomerDeliveryAddress>
                <Title />
                <Forename>Mike</Forename>
                <Surname>Hall</Surname>
                <Company>ABS Garages Ltd</Company>
                <Description>Mike Hall - NE56 4ER</Description>
                <Address1>Swanson Industries</Address1>
                <Address2>Dukes Industrial Estate</Address2>
                <Town>Whitley Bay</Town>
                <Postcode>NE56 4ER</Postcode>
                <County>North Tyneside</County>
                <Country>CH</Country>
                <Telephone>0191 232 2345</Telephone>
                <Fax>0191 245 3464</Fax>
                <Birthdate xsi:nil="true" />
                <Notes />
                <TaxCode>1</TaxCode>
                <CustomFields />
                <Activities />
                <Groups />
            </CustomerDeliveryAddress>
            <Analysis1>Trade</Analysis1>
            <Analysis2>George</Analysis2>
            <Analysis3>Tyne & Wear</Analysis3>
            <NominalCode>4000</NominalCode>
            <Department>1</Department>
            <OverrideNominalCode xsi:nil="true" />
            <TaxCode>1</TaxCode>
            <OverrideTaxCode>true</OverrideTaxCode>
            <Currency>GBP</Currency>
            <FixedDiscount>0</FixedDiscount>
            <LineDiscount xsi:nil="true" />
            <PriceListReference>TRADEB</PriceListReference>
            <DiscountType>InvoiceValue</DiscountType>
            <DiscountTable />
            <CreditLimit>4000</CreditLimit>
            <SettlementDays>30</SettlementDays>
            <SettlementDiscount>2.5</SettlementDiscount>
            <PaymentDays>30</PaymentDays>
            <Terms>30 Days</Terms>
            <CreditPosition>Good</CreditPosition>
            <AccountStatus>0</AccountStatus>
            <AccountStatusText>Open</AccountStatusText>
            <DUNSNumber>0</DUNSNumber>
            <TermsAgreed>true</TermsAgreed>
            <AccountOnHold>false</AccountOnHold>
            <AccountOpened>2000-12-13T00:00:00</AccountOpened>
            <LastCreditReview>2006-09-09T00:00:00</LastCreditReview>
            <NextCreditReview>2007-03-09T00:00:00</NextCreditReview>
            <ApplicationDate>2000-12-10T00:00:00</ApplicationDate>
            <DateReceived>2000-12-11T00:00:00</DateReceived>
            <LastInvoiceDate>2006-04-24T00:00:00</LastInvoiceDate>
            <LastPaymentDate>2006-04-27T00:00:00</LastPaymentDate>
            <TurnoverMTD>5603.76</TurnoverMTD>
            <TurnoverYTD>0</TurnoverYTD>
            <PriorYear>0</PriorYear>
            <Banks>
                <Bank>
                    <BankName />
                    <Address1 />
                    <Address2 />
                    <Town />
                    <County />
                    <Postcode />
                    <AccountName />
                    <SortCode />
                    <AccountNumber />
                    <BACSRef />
                    <IBAN />
                    <BICSwift />
                    <RollNumber />
                    <AdditionalRef1 />
                    <AdditionalRef2 />
                    <AdditionalRef3 />
                    <OnlineReceipts>false</OnlineReceipts>
                </Bank>
            </Banks>
            <Attachments />
            <Memo />
            <CreateOnly xsi:nil="true" />
            <Contacts />
            <DeliveryAddresses />
            <CustomFields />
            <AnalysisCodes />
            <Activities />
            <Groups />
            <Notes />
        </Customer>
    </Customers>
</Company>
```