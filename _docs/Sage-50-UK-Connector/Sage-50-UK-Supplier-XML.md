---
slug: sage-50-uk-supplier-xml
title: Sage 50 UK Supplier XML
---
The Import Suppliers task will allow you to generate a new Supplier in a new sage through Zynk's XML format. 

If you follow the below instructions on the XML format you will be able to customise your XML file to meet your needs. Whilst you can auto create a Supplier based on a setting on the Import Sales Orders/Invoices Task, if you are looking to specify precise things on the Supplier record in Sage it is always best to use a separate Import Suppliers task.

See the below sample Supplier file:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <SupplierInvoiceAddress>
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
      </SupplierInvoiceAddress>
      <SupplierDeliveryAddress>
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
      </SupplierDeliveryAddress>
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
    </Supplier>
  </Suppliers>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Details  
The fields below on the Details tab in Sage can be set via the XML. Depending on your configuration at the Task Settings level in Zynk, you may not need to specify an account reference for every supplier because they can be generated automatically through Zynk.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| -| Id | 123 | string | 255 | Optional |
| A/C | AccountReference | JOE001 | string | 8 | Required, depending on settings|
| Company Name | CompanyName | Zynk Software Limited | string | 60 | Optional  |
| Street 1 | Address1 | Nelson House, Fleming Business Centre | string | 60 | Optional |
| Street 2 | Address2 | Jesmond | string | 60 | Optional |
| Town | Town | Newcastle upon Tyne | string | 60 | Optional  |
| County  | County  | Tyne & Wear  | string  | 60  | Optional  |
| Post Code | Postcode | NE2 3AE | string | 60 | Optional |
| Country | Country | GB | string | 2 | Optional  |
| VAT Number | VatNumber | 796 5763 59 | string | 30  | Optional  |
| Contact Name | FullName* | Mr Joe E Harrison Jr. | string | 30  | Optional  |
| -  | Title  | Mr  | string  | -  | Optional  |
| -  | Forename  | Joe  | string  | -  | Optional  |
| -  | Middlename  | E  | string  | -  | Optional  |
| -  | Surname  | Harrison  | string  | -  | Optional  |
| -  | Suffix  | Jr.  | string  | -  | Optional  |
| Trade Contact | TradeContact | Joe Harrison | string  | 30  | Optional  |
| Telephone | Telephone | 0845 123 2920 | string  | 30  | Optional |
| Telephone 2 | Mobile | 0777 777 7777  | string  | 30  | Optional  |
| Fax | Fax | 0845 123 2921 | string  | 30  | Optional  |
| Website | Website | http://www.zynk.com/ | string | 255  | Optional  |
| Email | Email | support@zynk.com | string  | 255 | Optional  |
| Electronic Letters | SendElectronicLetter  | true  | bool  | -  | Optional  |
| Electronic Invoices | SendElectronicInvoice  | true  | bool  | -  | Optional   |

*   FullName* - This field is not set directly in the XML, but is built up of Title, Forename, Middlename, Surname and Suffix.

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <SupplierInvoiceAddress>
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
      </SupplierInvoiceAddress>
      <VatNumber>796 5763 59</VatNumber>
      <SendElectronicInvoice>true</SendElectronicInvoice>
      <SendElectronicLetter>true</SendElectronicLetter>
    </Supplier>
  </Suppliers>
</Company>
```

## Defaults  
The below information will appear on the Defaults tab of the Supplier record in Sage 50. This is all optional information when building your Supplier Import XML, none of the below fields are mandatory when importing a Supplier.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Analysis 1 | Analysis1  | North East  | string  | 30  | Optional  |
| Analysis 2  | Analysis2  | Support  | string  | 30  | Optional  |
| Analysis 3  | Analysis3  | 01/01/2014  | string  | 30  | Optional  |
| Discount %  | FixedDiscount  | 10  | double  | -  | Optional  |
| Default Nominal Code  | NominalCode  | 4000  | string  | 8  | Optional  | If not specified when creating a supplier, the nominal code will be set to the default configured in Sage. |
| Default Tax Code  | TaxCode  | 1  | int  | 2  | Optional  | If not specified when creating a supplier, the tax code will be set to the default configured in Sage. |
| Currency  | Currency | GBP  | string  | 2  | Optional  | This field can only be set when creating a new supplier |
| Department | DepartmentInfo/Reference | 4 | int  | 3 | Optional | If not specified when creating a supplier, the department will be set to the default configured in Sage.|
| Department | DepartmentInfo/Name | Admin | string | 60 | Optional | If not specified when creating a supplier, the department will be set to the default configured in Sage. |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>  
      <Analysis1>North East</Analysis1>
      <Analysis2>Support</Analysis2>
      <Analysis3>01/01/2013</Analysis3>
      <FixedDiscount>10</FixedDiscount>
      <NominalCode>4000</NominalCode>
      <TaxCode>1</TaxCode>
      <Currency>GBP</Currency>
      <DepartmentInfo>
        <Reference>4</Reference>
        <Name>Admin</Name>
      </DepartmentInfo>
   </Supplier>
 </Suppliers>
</Company>
```

Credit Control
When importing a Supplier record you can also set fields on the Credit Control tab like Account Status, Terms Agreed and more.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Credit Limit  | CreditLimit  | 1000  | double  | -  | Optional  |
| Priority Supplier | Priority  | true  | bool  | -  | Optional  |
| Account Status  | AccountStatus*  | 0  | int  | 2  | Optional  |
| Terms Agreed  | TermsAgreed  | true  | bool  | -  | Optional  |

*   AccountStatus* - This field is only set when creating a new customer.

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <CreditLimit>1000</CreditLimit>
      <Priority>true</Priority>
      <AccountStatus>0</AccountStatus>
      <TermsAgreed>true</TermsAgreed>
    </Supplier>
  </Suppliers>
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
  <Suppliers>
    <Supplier>
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
    </Supplier>
  </Suppliers>
</Company>
```