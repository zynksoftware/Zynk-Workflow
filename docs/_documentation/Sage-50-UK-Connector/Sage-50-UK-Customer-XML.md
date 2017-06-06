---
slug: sage-50-uk-customer-xml
title: Sage 50 UK Customer XML
---
The customers task allows you to export new (customers created since the last time the task ran), modified (both new and updated customers since the last time the task ran), or all customers.  You can also create new and update existing customers in Sage 50.  We recommend that the `Id` field be populated by the unique id of the customers from the external system, Zynk uses this field to track customers already imported to prevent duplicates being created in Sage.  By default Zynk will use the account reference to lookup customer records in Sage 50, but you can also configured other lookup fields e.g. email address or postcode.

Any Sage 50 fields not documented below are not supported with our imports / exports.  Examples of where in the XML the fields should appear are shown in the samples below.

Minimal customer file:
```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
    </Customer>
  </Customers>
</Company>
```

Sample customer file:
```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <CustomerInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
        <Email>support@zynk.com</Email>
        <Website>www.zynk.com</Website>
      </CustomerInvoiceAddress>
      <CustomerDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
      </CustomerDeliveryAddress>
      <Analysis1>North East</Analysis1>
      <NominalCode>4000</NominalCode>
      <DepartmentInfo>
        <Reference>4</Reference>
        <Name>Admin</Name>
      </DepartmentInfo>
      <OverrideNominalCode xsi:nil="true" />
      <TaxCode>4</TaxCode>
      <Currency>GBP</Currency>
      <TermsAgreed>true</TermsAgreed>
      <AccountOnHold>false</AccountOnHold>
      <RestrictMailing>true</RestrictMailing>
    </Customer>
  </Customers>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Customer Records - Details  
The most critical customer information is contained on the details tab, covering account detail, registered address, contact information as well as email settings and addresses.
Note that depending on your configuration at the Task Settings level in Zynk you do not need to specify an account reference for every customer as you can create them automatically through Zynk.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| -  | Id | 123 | string | 255 | Optional |   |
| A/C | AccountReference | JOE001 | string | 8 | Dependant | Required if the Auto Generate References setting is not enabled in the task's settings.  |
| Company Name | CompanyName | Zynk Software Limited | string | 60 | Dependant | Required unless a Title, Forename, Middlename or Surname is provided. If a value is not provided, it will be set to the Title, Forename, Middlename, Surname and Suffix. |
| Street 1 | Address1 | Nelson House, Fleming Business Centre | string | 60 | Optional |   |
| Street 2 | Address2 | Jesmond | string | 60 | Optional |   |
| Town | Town | Newcastle upon Tyne | string | 60 | Optional  |   |
| County  | County  | Tyne and Wear  | string  | 60  | Optional  |   |
| Post Code | Postcode | NE2 3AE | string | 60 | Optional |   |
| Country | Country | GB | string | 2 | Optional  |   |
| VAT Number | VatNumber | 796 5763 59 | string | 30  | Optional  |   |
| Contact Name | FullName | Mr Joe E Harrison Jr. | string | 30  | Optional  | This field is not set directly in the XML, but is built up of Title, Forename, Middlename, Surname and Suffix. |
| -  | Title  | Mr  | string  | -  | Optional  |   |
| -  | Forename  | Joe  | string  | -  | Optional  |   |
| -  | Middlename  | E  | string  | -  | Optional  |   |
| -  | Surname  | Harrison  | string  | -  | Optional  |   |
| -  | Suffix  | Jr.  | string  | -  | Optional  |   |
| Trade Contact | TradeContact | Joe Harrison | string  | 30  | Optional  |   |
| Telephone | Telephone | 0845 123 2920 | string  | 30  | Optional |   |
| Telephone 2 | Mobile | 0777 777 7777  | string  | 30  | Optional  |   |
| Fax | Fax | 0845 123 2921 | string  | 30  | Optional  |   |
| Website | Website | [www.zynk.com](http://www.zynk.com/) | string | 255  | Optional  |   |
| Email | Email | support@zynk.com | string  | 255 | Optional  |   |
| Electronic Letters | SendElectronicLetter  | true  | bool  | -  | Optional  |   |
| Electronic Invoices | SendElectronicInvoice  | true  | bool  | -  | Optional   |   |  

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <CustomerInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Suffix>Jr.</Suffix>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
        <Fax>0845 123 2921</Fax>
        <Mobile>0777 777 7777</Mobile>
        <Email>support@zynk.com</Email>
        <Website>www.zynk.com</Website>
        <TradeContact>Joe Harrison</TradeContact>
      </CustomerInvoiceAddress>
      <VatNumber>796 5763 59</VatNumber>
      <SendElectronicInvoice>true</SendElectronicInvoice>
      <SendElectronicLetter>true</SendElectronicLetter>
    </Customer>
  </Customers>
</Company>
```

## Defaults  
The below information will appear on the Defaults tab of the Customer record in Sage 50. This is all optional information when building your Customer Import XML, none of the below fields are mandatory when importing a Customer.



| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Analysis 1 | Analysis1  | North East  | string  | 30  | Optional  |   |
| Analysis 2  | Analysis2  | Support  | string  | 30  | Optional  |   |
| Analysis 3  | Analysis3  | 01/01/2014  | string  | 30  | Optional  |   |
| Discount %  | FixedDiscount  | 10  | double  | -  | Optional  |   |
| Additional Discount  | DiscountType | DiscountTable  | enum  | -  | Optional  | This field value can be either NoDiscount, InvoiceValue or DiscountTable.   |
| -  | DiscountTable  | A  | string  | 1  | Dependant   
 | If DiscountType is set to DiscountTable, a value is required for this field.  |
| Price List | PriceListReference  | TRADEA  | string  | 8  | Optional  |   |
| Default Nominal Code  | NominalCode  | 4000  | string  | 8  | Optional  | If not specified when creating a customer, the nominal code will be set to the default configured in Sage.   |
| Use Nominal Code  | OverrideNominalCode  | false  | bool  | -  | Optional  |   |
| Default Tax Code  | TaxCode  | 1  | int  | 2  | Optional  | If not specified when creating a customer, the tax code will be set to the default configured in Sage. |
| Use Tax Code  | OverrideTaxCode  | false  | bool  | -  | Optional  |   |
| Currency  | Currency | GBP  | string  | 2  | Optional  | This field can only be set when creating a new customer. If not specified, the currency will be set to the                default configured in Sage. |
| Department  | DepartmentInfo/Reference | 4  | int  | 3  | Optional   | If not specified when creating a customer, the department will be set to the default configured in Sage.  |
| Department   | DepartmentInfo/Name | Admin   | string   | 60 | Optional   | If not specified when creating a customer, the department will be set to the default configured in Sage.   |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>      
      <Analysis1>North East</Analysis1>
      <Analysis2>Support</Analysis2>
      <Analysis3>01/01/2013</Analysis3>
      <FixedDiscount>10</FixedDiscount>
      <DiscountType>DiscountTable</DiscountType>
      <DiscountTable>A</DiscountTable>
      <PriceListReference>TRADEA</PriceListReference>
      <NominalCode>4000</NominalCode>
      <OverrideNominalCode>false</OverrideNominalCode>
      <TaxCode>1</TaxCode>
      <OverrideTaxCode>false</OverrideTaxCode>
      <Currency>GBP</Currency>
      <DepartmentInfo>
        <Reference>4</Reference>
        <Name>Admin</Name>
      </DepartmentInfo>
    </Customer>
  </Customers>
</Company>
```

## Credit Control  
When importing a Customer record you can also set fields on the Credit Control tab like Account Status, Terms Agreed and many more.  

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- | 
| Credit Limit  | CreditLimit  | 1000  | double  | -  | Optional  |
| Settlement Due  | SettlementDays  | 30  | int  | 2  | Optional  |
| Sett. Discount  | SettlementDiscount  | 2.5  | double  | -  | Optional  |
| Payment Due  | PaymentDays  | 30  | double  | -  | Optional  |
| Trading Terms  | Terms  | 30 Days Strictly Net  | string  | 30  | Optional  |
| Account Status  | AccountStatus  | 0  | int  | 2  | Optional  |
| DUNS Number   | DUNSNumber  | 0 | string  | 9  | Optional  |
| Terms Agreed  | TermsAgreed  | true  | bool  | -  | Optional  |
| Account On Hold | AccountOnHold  | false  | bool  | -  | Optional  |
| A/C Opened  | AccountOpened\*  | 2014-01-01T00:00:00  | datetime  | -  | Optional  |
| Memo  | Memo  | Testing account  | string  | -  | Optional  |
| Restrict Mailing  | RestrictMailing  | true  | bool  | -  | Optional  |  

* AccountOpened* - This field is only set when creating a new customer.  If this field is not provided it will default to the current date.

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <CreditLimit>1000</CreditLimit>
      <SettlementDays>30</SettlementDays>
      <SettlementDiscount>2.5</SettlementDiscount>
      <PaymentDays>30</PaymentDays>
      <Terms>30 Days Strictly Net</Terms>
      <AccountStatus>0</AccountStatus>
      <DUNSNumber>0</DUNSNumber>
      <TermsAgreed>true</TermsAgreed>
      <AccountOnHold>false</AccountOnHold>
      <Memo>Testing account</Memo>
      <RestrictMailing>true</RestrictMailing>
   </Customer>
 </Customers>
</Company>
```

## Bank  
Bank information on the Customer record can also be set via XML, see the node information below.



| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- | 
| Bank Name  | BankName  | -  | string  | 60  | Optional  |
| Street 1  | Address1  | -  | string  | 60  | Optional  |
| Street 2  | Address2  | -  | string  | 60  | Optional  |
| Town  | Town  | -  | string  | 60  | Optional  |
| County  | County  | -  | string  | 60  | Optional  |
| Post Code  | Postcode  | -  | string  | 60  | Optional  |
| Account Name  | AccountName  | - | string  | 60  | Optional  |
| Sort Code  | SortCode  | -  | string  | 10  | Optional  |
| Account Number  | AccountNumber  | -  | string  | 60  | Optional  |
| BACS Ref  | BACSRef  | -  | string  | 60  | Optional  |
| IBAN  | IBAN  | -  | string  | 60  | Optional  |
| BIC/Swift | BICSwift  | -  | string  | 60  | Optional  |
| Roll Number  | RollNumber  | -  | string  | 60  | Optional  |
| Additional Ref 1  | AdditionalRef1  | -  | string  | 60  | Optional  |
| Additional Ref 2  | AdditionalRef2  | -  | string  | 60  | Optional  |
| Additional Ref 3  | AdditionalRef3  | -  | string  | 60  | Optional  |
| Online Receipts  | OnlineReceipts  | false  | bool  | -  | Optional  |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
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
    </Customer>
  </Customers>
</Company>
```