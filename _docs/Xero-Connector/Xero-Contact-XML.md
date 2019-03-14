---
slug: xero-contact-xml
title: Xero Contact XML
---
The Upsert Contacts task allows you to create new and update existing contacts in Xero. We recommend that the ExternalId field be populated by the unique ID of the customers from the source system, Zynk uses this field to track contacts already imported to prevent duplicates being created in Xero.   

Any Xero fields not documented below are not supported with our imports.  Examples of where in the XML the fields should appear are shown in the samples below. 

Sample import file for creating or updating a contact:

```xml
<?xml version="1.0"?>
<ArrayOfXeroContact>
  <XeroContact>
    <Id>cea98f0f-af1a-4b23-ac1b-9584ba014dcb</Id>
    <ExternalId>52380</ExternalId>
    <ContactNumber>A1D001</ContactNumber>
    <ContactStatus>Active</ContactStatus>
    <Name>A1 Design Services</Name>
    <AccountNumber>A1D001</AccountNumber>
    <FirstName>Lee</FirstName>
    <LastName>Dalkin</LastName>
    <EmailAddress>newbusinessadvice@sage.com</EmailAddress>
    <BankAccountDetails />
    <DefaultCurrency>GBP</DefaultCurrency>
    <HasAttachments>false</HasAttachments>
    <ContactPersons />
    <Addresses>
      <Address>
        <AddressType>PostOfficeBox</AddressType>
        <AddressLine1>67a Station Road</AddressLine1>
        <AddressLine2 />
        <AddressLine3 />
        <City>Blackpool</City>
        <Region>Lancashire</Region>
        <PostalCode>BP12 7HT</PostalCode>
        <Country>GB</Country>
        <AttentionTo>Lee Dalkin</AttentionTo>
      </Address>
      <Address>
        <AddressType>Street</AddressType>
        <AddressLine1>67a Station Road</AddressLine1>
        <AddressLine2 />
        <AddressLine3 />
        <City>Blackpool</City>
        <Region>Lancashire</Region>
        <PostalCode>BP12 7HT</PostalCode>
        <Country>GB</Country>
        <AttentionTo>Lee Dalkin</AttentionTo>
      </Address>
    </Addresses>
    <Phones>
      <Phone>
        <PhoneType>Default</PhoneType>
        <PhoneNumber>01742 876 234</PhoneNumber>
        <PhoneAreaCode />
        <PhoneCountryCode />
      </Phone>
    </Phones>
    <ContactGroups />
  </XeroContact>
</ArrayOfXeroContact>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the XML schema is used below as a reference of where fields should be in the object model.

## Matching Contacts
Any of the following fields can be used to match the contacts provided in the XML to existing contacts in Xero. At least one should be provided, to prevent contacts being duplicated in Xero.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Contact ID | Id | cea98f0f-af1a-4b23-ac1b-9584ba014dcb | guid | 255 | Optional |
| - | ExternalId | 52380 | string | 255 | Optional | Zynk stores a mapping between Xero's contact ID and the ExternalId, and will use this to look up the contact ID. |
| Contact Code | ContactNumber | A1D001 | string | 50 | Optional | This field cannot be set manually by the user. It can only be set via Zynk or other applications which use the Xero API. |

```xml
<?xml version="1.0"?>
<ArrayOfXeroContact>
  <XeroContact>
    <Id>cea98f0f-af1a-4b23-ac1b-9584ba014dcb</Id>
    <ExternalId>52380</ExternalId>
    <ContactNumber>A1D001</ContactNumber>
  </XeroContact>
</ArrayOfXeroContact>
```

## Contact Information
The following fields can be set in the contact information section.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Contact Name | Name | A1 Design Services | string | 255 | Required |
| Account Number | AccountNumber | A1D001 | string | 50 | Optional |
| Primary Person > Name > First | FirstName | Lee | string | 255 | Optional |
| Primary Person > Name > Last | LastName | Dalkin | string | 255 | Optional |
| Primary Person > Email | EmailAddress | newbusinessadvice@sage.com | string | 255 | Optional |
| Person > Name > First | ContactPersons/ContactPerson/FirstName | John | string | 255 | Optional |
| Person > Name > Last | ContactPersons/ContactPerson/LastName | Smith | string | 255 | Optional |
| Person > Email |  ContactPersons/ContactPerson/EmailAddress | john.smith@example.com | string | 255 | Optional |
|  - | Phones/Phone/PhoneType | Default | enum | - | Required | This field determines the type of the phone number. Possible values are: Default, DirectDial, Mobile, Fax. |
| Phone/Fax/Mobile/Direct Dial > Country | Phones/Phone/PhoneCountryCode | +44 | string | 20 | Optional |
| Phone/Fax/Mobile/Direct Dial > Area | Phones/Phone/PhoneAreaCode | 0191 | string | 10 | Optional |
| Phone/Fax/Mobile/Direct Dial > Number | Phones/Phone/PhoneNumber | 123 2920 | string | 50 | Optional |
| Skype Name/Number | SkypeUserName | lee_dalkin | string | 255 | Optional |
| Website | Website | http://www.zynk.com | string | 255 | Optional |
| - | Addresses/Address/AddressType | PostOfficeBox | enum | - | Required | This field determines the type of the address. Possible values are: PostOfficeBox, Street. |
| Address > Attention | Addresses/Address/AttentionTo | Lee Dalkin | string | 255 | Optional |
| Address > Address | Addresses/Address/AddressLine1 | Zynk Software | string | 500 | Optional |
| Address > Address | Addresses/Address/AddressLine2 | i6 Building | string | 500 | Optional |
| Address > Address | Addresses/Address/AddressLine3 | 6-8 Charlotte Square | string | 500 | Optional |
| Address > Address | Addresses/Address/AddressLine4 | string | 500 | Optional |
| Address > City/Town | Addresses/Address/City | Newcastle | string | 255 | Optional |
| Address > State/Region | Addresses/Address/Region | Tyne & Wear | string | 255 | Optional |
| Address > Postal/Zip Code | Addresses/Address/PostalCode | NE1 4XF | string | 50 | Optional |
| Address > Country | Addresses/Address/Country | GB | string | 50 | Optional |
| Contact Status | ContactStatus | Active | enum |  - | Optional | Possible values are: Active, Archived. Will default to Active if not provided. |

```xml
<?xml version="1.0"?>
<ArrayOfXeroContact>
  <XeroContact>
    <Name>A1 Design Services</Name>
    <AccountNumber>A1D001</AccountNumber>
    <FirstName>Lee</FirstName>
    <LastName>Dalkin</LastName>
    <EmailAddress>newbusinessadvice@sage.com</EmailAddress>
    <ContactPersons>
      <ContactPerson>
        <FirstName>John</FirstName>
        <LastName>Smith</LastName>
        <EmailAddress>john.smith@example.com</EmailAddress>
      </ContactPersons>
    </ContactPersons>
    <Phones>
      <Phone>
        <PhoneType>Default</PhoneType>
        <PhoneCountryCode>+44</PhoneCountryCode>
        <PhoneAreaCode>0191</PhoneAreaCode>
        <PhoneNumber>123 2920</PhoneNumber>
      </Phone>
    </Phones>
    <SkypeUserName>lee_dalkin</SkypeUserName>
    <Website>www.zynk.com</Website>
    <Addresses>
      <Address>
        <AddressType>PostOfficeBox</AddressType>
        <AttentionTo>Lee Dalkin</AttentionTo>
        <AddressLine1>Zynk Software</AddressLine1>
        <AddressLine2>i6 Building</AddressLine2>
        <AddressLine3>6-8 Charlotte Square</AddressLine3>
        <AddressLine4></AddressLine4>
        <City>Newcastle</City>
        <Region>Tyne & Wear</Region>
        <PostalCode>NE1 4XF</PostalCode>
        <Country>GB</Country>
      </Address>
      <Address>
        <AddressType>Street</AddressType>
        <AttentionTo>Lee Dalkin</AttentionTo>
        <AddressLine1>Zynk Software</AddressLine1>
        <AddressLine2>i6 Building</AddressLine2>
        <AddressLine3>6-8 Charlotte Square</AddressLine3>
        <AddressLine4></AddressLine4>
        <City>Newcastle</City>
        <Region>Tyne & Wear</Region>
        <PostalCode>NE1 4XF</PostalCode>
        <Country>GB</Country>
      </Address>
    </Addresses>
    <ContactStatus>Active</ContactStatus>
  </XeroContact>
</ArrayOfXeroContact>
```

## Financial Information
The following fields can be set in the financial information section.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Sales Settings > Default Account | SalesAccountCode | 200 | string | 10 | Optional |
| Sales Settings > Default Region | SalesTrackingCategories/SalesTrackingCategory/Option | North | string | 50 | Optional |
| Purchase Settings > Default Account | PurchaseAccountCode | 300 | string | 10 | Optional |
| Purchase Settings > Default Region | PurchasesTrackingCategories/PurchasesTrackingCategory/Option | North | string | 50 | Optional |
| VAT > Tax Number | TaxNumber | 19283419 | string | 50 | Optional |
| VAT > Default Sales VAT | AccountsReceivableTaxType | OUTPUT2 | string | - | Optional | See [Xero's Documentation](https://developer.xero.com/documentation/api/types#TaxTypes) for a list of tax types. |
| VAT > Default Purchase VAT | AccountsPayableTaxType | INPUT2 | string | - | Optional | See [Xero's Documentation](https://developer.xero.com/documentation/api/types#TaxTypes) for a list of tax types. |
| Currency | DefaultCurrency | GBP | string | 3 | Optional | Use the three-letter ISO currency code. |
| Bills Due Date > Day | PaymentTerms/Bills/Day | 10 | int | - | Optional |
| Bills Due Date > Term | PaymentTerms/Bills/TermType | AfterBillDate | enum | - | Optional | Possible values are: FollowingMonth, AfterBillDate, CurrentMonth, DaysAfterBillMonth, AfterInvoiceMonth. |
| Invoices Due Date > Day | PaymentTerms/Sales/Day | 10 | int | - | Optional |
| Invoices Due Date > Term | PaymentTerms/Sales/TermType | AfterBillDate | enum | - | Optional | Possible values are: FollowingMonth, AfterBillDate, CurrentMonth, DaysAfterBillMonth, AfterInvoiceMonth. |
| Xero Network Key | XeroNetworkKey | abd523e | string | Optional |

```xml
<?xml version="1.0"?>
<ArrayOfXeroContact>
  <XeroContact>
    <SalesAccountCode>200</SalesAccountCode>
    <SalesTrackingCategories>
      <SalesTrackingCategory>
        <Name>Region</Name>
        <Option>North</Option>
      </SalesTrackingCategory>
    </SalesTrackingCategories>
    <PurchaseAccountCode>300</PurchaseAccountCode>
    <PurchasesTrackingCategories>
      <PurchasesTrackingCategory>
        <Name>Region</Name>
        <Option>North</Option>
      </PurchasesTrackingCategory>
    </PurchasesTrackingCategories>
    <TaxNumber>19283419</TaxNumber>
    <AccountsReceivableTaxType>OUTPUT2</AccountsReceivableTaxType>
    <AccountsPayableTaxType>INPUT2</AccountsPayableTaxType>
    <DefaultCurrency>GBP</DefaultCurrency>
    <PaymentTerms>
      <Bills>
        <Day>10</Day>
        <TermType>AfterBillDate</TermType>
      </Bills>
      <Sales>
        <Day>10</Day>
        <TermType>AfterBillDate</TermType>
      </Sales>
    </PaymentTerms>
    <XeroNetworkKey>abd523e</XeroNetworkKey>
  </XeroContact>
</ArrayOfXeroContact>
```

## Attachments
You can attach up to 10 files to a contact in Xero. If the same file name is provided as an attachment already on the contact in Xero, the existing file will be overwritten.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | FilePath | C:\10388.png | string | - | Required | The path of the file to upload to Xero |
| Name | FileName | upload.png | string | - | Optional | Will default to the file name specified in the FilePath if not provided |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroContact>
  <XeroContact>
    <Attachments>
      <Attachment>
        <FilePath>C:\10388.png</FilePath>
        <FileName>upload.png</FileName>
      </Attachment>
    </Attachments>
  </XeroContact>
</ArrayOfXeroContact>
```