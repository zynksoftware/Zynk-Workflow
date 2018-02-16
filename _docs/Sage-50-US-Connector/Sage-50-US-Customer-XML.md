---
slug: sage-50-us-customer-xml
title: Sage 50 US Customer XML
---
Import Customers allows you to create new and update existing customers in Sage 50 US.  We recommend that the ExternalId field be populated by the unique id of the customer from the external system, Zynk uses this field to track customers already imported to prevent duplicates being created in Sage.   

Any Sage fields not documented below are not supported with our imports, if there are additional fields you need contact us at support@zynk.com.

Complete import file for creating a customer:-

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>123</ExternalId>
    <Id>ALDRED</Id>
    <Name>Aldred Builders, Inc.</Name>
    <IsInactive>false</IsInactive>
    <AccountNumber />
    <Category>LAND</Category>
    <CustomFields>
      <CustomField>
        <Name>Sales Contact</Name>
        <Value />
      </CustomField>
      <CustomField>
        <Name>Lawn Care Srvc?</Name>
        <Value>Yes</Value>
      </CustomField>
      <CustomField>
        <Name>Monthly Service?</Name>
        <Value>Yes</Value>
      </CustomField>
      <CustomField>
        <Name>Qtrly Mailing?</Name>
        <Value>Yes</Value>
      </CustomField>
      <CustomField>
        <Name>Referral</Name>
        <Value>Internet</Value>
      </CustomField>
    </CustomFields>
    <ShipVia>None</ShipVia>
    <UseEmailToDeliverForms>false</UseEmailToDeliverForms>
    <ReplaceInventoryItemIDWithUPC>false</ReplaceInventoryItemIDWithUPC>
    <ReplaceInventoryItemIDWithPartNumber>false</ReplaceInventoryItemIDWithPartNumber>
    <PaymentMethod>Check</PaymentMethod>
    <CashAccountReference>10200-00</CashAccountReference>
    <Terms>
      <ChargeInterest>true</ChargeInterest>
      <CreditLimit>50000.00</CreditLimit>
      <DiscountDays>10</DiscountDays>
      <DiscountPercent>2.00</DiscountPercent>
      <DueDays>30</DueDays>
      <IsStandardTerms>false</IsStandardTerms>
      <PaymentTimeFrame>DueInNumberOfDays</PaymentTimeFrame>
      <UseDiscounts>true</UseDiscounts>
    </Terms>
    <IsProspect>false</IsProspect>
    <BillToContact>
      <Prefix />
      <FirstName>Tony</FirstName>
      <MiddleInitial />
      <LastName>Aldred</LastName>
      <Suffix />
      <CompanyName>Aldred Builders, Inc.</CompanyName>
      <Title />
      <Telephone1>770-555-0654</Telephone1>
      <Telephone2>770-555-0655</Telephone2>
      <Fax>770-555-0656</Fax>
      <Email>taldred@sample.sage.com</Email>
      <Gender>NotSpecified</Gender>
      <NameToUseOnForms>CompanyName</NameToUseOnForms>
      <Address>
        <Address1>412 Sever Rd</Address1>
        <Address2 />
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30092</Zip>
        <Country />
        <SalesTaxCode>GAGWINN</SalesTaxCode>
      </Address>
      <Notes />
    </BillToContact>
    <ShipToContact>
      <Prefix />
      <FirstName>Tammy</FirstName>
      <MiddleInitial />
      <LastName>Aldred</LastName>
      <Suffix />
      <CompanyName>Aldred Builders, Inc.</CompanyName>
      <Title>Bookkeeper</Title>
      <Telephone1>770-555-0657</Telephone1>
      <Telephone2>770-555-0658</Telephone2>
      <Fax>770-555-0659</Fax>
      <Email>tammyaldred@sample.sage.com</Email>
      <Gender>NotSpecified</Gender>
      <NameToUseOnForms>ContactName</NameToUseOnForms>
      <Address>
        <Address1>412 Sever Rd</Address1>
        <Address2 />
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30092</Zip>
        <Country />
        <SalesTaxCode>GAGWINN</SalesTaxCode>
      </Address>
      <Notes />
    </ShipToContact>
    <CustomerSince>2011-03-15T00:00:00</CustomerSince>
    <SalesRepresentativeReference>DGROSS</SalesRepresentativeReference>
    <UsualSalesAccountReference>40000-00</UsualSalesAccountReference>
    <OpenPurchaseOrderNumber />
    <ResaleNumber />
    <PriceLevel>Price Level 1</PriceLevel>
    <CreditStatus>NotifyOverLimit</CreditStatus>
  </Customer>
</ArrayOfCustomer>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read.  The sections have been broken up into the various sections of the customer record as viewed within Sage 50 US.

## Main Customer Fields
The below will let you specify the main fields required for a customer record.  Note that depending on your configuration at the Task Settings level in Zynk you may not need to specify an Id field as you can create them automatically through Zynk as part of the import.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| N/A | ExternalId | 123 | string | 255 | Optional |
| Customer ID | Id | ALDRED | string | 20 | Required when not using auto generate settings |
| Name | Name | Aldred Builders, Inc.  | string | 40 | Required when using auto generate settings |
| Prospect | IsProspect | false | bool | - | Optional |
| Inactive | IsInactive | false | bool | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId />
    <Id>ALDRED</Id>
    <Name>Aldred Builders, Inc.</Name>
    <IsProspect>false</IsProspect>
    <IsInactive>false</IsInactive>
  </Customer>
</ArrayOfCustomer>
```

## General Fields
The below will let you specify the fields on the General tab in Sage.  Note the names of the custom fields depend on what you have called the fields within Sage, and must be provided within the CustomFields node.  Please see Bill To Contact section below for any fields relating to that contact.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Account number | AccountNumber | ALDRED | string | 25 | Optional |
| Customer type | Category | LAND | string | 8 | Optional |
| Custom Field Label | CustomField/Name | Referral | string | 26 | Optional |
| Custom Field Value | CustomField/Value | Internet | string | 40 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <AccountNumber>ALDRED</AccountNumber>
    <Category>LAND</Category>
    <CustomFields>
      <CustomField>
        <Name>Referral</Name>
        <Value>Internet</Value>
      </CustomField>
    </CustomFields>
  </Customer>
</ArrayOfCustomer>
```

## Bill To Contact Fields
The below will let you specify the fields for the bill to contact in Sage.  Note the details of the bill to contact are what are shown on the General tab.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Title | Prefix | string | 4 | Optional |
| First | FirstName | Tony | string | 15 | Optional |
| MI | MiddleInitial | string | 1 | Optional |
| Last | LastName | Aldred | string | 20 | Optional |
| Suffix | Suffix | string | 4 | Optional |
| Company name | CompanyName | Aldred Builders, Inc.  | string | 39 | Required |
| Job title | Title | Owner | string | 30 | Optional |
| Telephone 1 | Telephone1 | 770-555-0654  | string   | 20 | Optional   |
| Telephone 2 | Telephone2 | 770-555-0655  | string   | 20 | Optional   |
| Fax | Fax | 770-555-0656  | string   | 20 | Optional   |
| E-mail | Email | taldred@sample.sage.com | string  | 64 | Optional |
| Gender | Gender* | Male | enum | - | Optional |
| Ship to address name | NameToUseOnForms* | CompanyName  | enum  | -   | Optional   |
| Address Line 1 | Address/ Address1 | 412 Sever Rd  | string  | 30 | Optional |
| Address Line 2  | Address/Address2  | string | 30 | Optional |
| City   | Address/City  | Norcross  | string | 20 | Optional |
| ST | Address/State  | GA  | string | 2 | Optional |
| Zip Code | Address/Zip  | 30092  | string | 12 | Optional |
| Country | Address/Country  | string | 15 | Optional |
| Sales Tax* | Address/SalesTaxCode  | GAGWINN  | string | 8 | Optional |

*   Gender* - can be NotSpecified, Male or Female
*   NameToUseOnForms* - can be ContactName or CompanyName
*   Sales Tax* - can only be what you have setup in Sage under Maintain -> Sales Taxes

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <BillToContact>
      <Prefix />
      <FirstName>Tony</FirstName>
      <MiddleInitial />
      <LastName>Aldred</LastName>
      <Suffix />
      <CompanyName>Aldred Builders, Inc.</CompanyName>
      <Title />
      <Telephone1>770-555-0654</Telephone1>
      <Telephone2>770-555-0655</Telephone2>
      <Fax>770-555-0656</Fax>
      <Email>taldred@sample.sage.com</Email>
      <Gender>NotSpecified</Gender>
      <NameToUseOnForms>CompanyName</NameToUseOnForms>
      <Address>
        <Address1>412 Sever Rd</Address1>
        <Address2 />
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30092</Zip>
        <Country />
        <SalesTaxCode>GAGWINN</SalesTaxCode>
      </Address>
      <Notes />
    </BillToContact>
  </Customer>
</ArrayOfCustomer>
```

## Ship To Contact Fields
The ship to contact uses the exact same structure as the bill to contact, except it is within a ShipToContact node in the XML.

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ShipToContact>
      <Prefix />
      <FirstName>Tammy</FirstName>
      <MiddleInitial />
      <LastName>Aldred</LastName>
      <Suffix />
      <CompanyName>Aldred Builders, Inc.</CompanyName>
      <Title>Bookkeeper</Title>
      <Telephone1>770-555-0657</Telephone1>
      <Telephone2>770-555-0658</Telephone2>
      <Fax>770-555-0659</Fax>
      <Email>tammyaldred@sample.sage.com</Email>
      <Gender>NotSpecified</Gender>
      <NameToUseOnForms>ContactName</NameToUseOnForms>
      <Address>
        <Address1>412 Sever Rd</Address1>
        <Address2 />
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30092</Zip>
        <Country />
        <SalesTaxCode>GAGWINN</SalesTaxCode>
      </Address>
      <Notes />
    </ShipToContact>
  </Customer>
</ArrayOfCustomer>
```

## History Fields
The below will let you specify the fields on the History tab in Sage.  Note the majority of fields on this tab are read only, so will only be used in future exports of customer data.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Customer since | CustomerSince | 2011-03-15T00:00:00 | datetime | - | Optional |

```xml
xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <CustomerSince>2011-03-15T00:00:00</CustomerSince>
  </Customer>
</ArrayOfCustomer>
```

## Sales Info Fields
The below will let you specify the fields on the Sales Info tab in Sage. 

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Sales rep* | SalesRepresentativeReference | DGROSS | string | 20 | Optional |
| GL sales account* | UsualSalesAccountReference | 40000-00 | string | 15 | Optional |
| Open PO number | OpenPurchaseOrderNumber | string | 20 | Optional |
| Ship via* | ShipVia | None | string | 20 | Optional |
| Resale number | ResaleNumber | string | 20 | Optional |
| Pricing level* | PriceLevel | Price Level 1 | string | 14 | Optional |
| Batch delivery method | UseEmailToDeliverForms* | false | bool | - | Optional |
| Replace item ID with* | ReplaceInventoryItemIDWithUPC | false | bool | - | Optional |
| | ReplaceInventoryItemIDWithPartNumber | false | bool | - | Optional |

*   Sales rep* - can only be what you have setup in Sage under Maintain Employees & Sales Reps. 
*   GL sales account* - can only be what you have setup in Sage under Maintain Chart of Accounts. 
*   Ship via* - can only be what you have setup in Inventory Item Defaults on the Taxes/Shipping tab
*   Pricing level* - can only be what you have setup on the Price Levels tab in Inventory Item Defaults
*   UseEmailToDeliverForms* - set to false to use Paper form, set to true to use E-mail
*   Replace item ID with*
  *   To uncheck all options set both ReplaceInventoryItemIDWithUPC and ReplaceInventoryItemIDWithPartNumber to false
  *   To check option and set to UPC/SKU set ReplaceInventoryItemIDWithUPC to true
  *   To check option and set to Part number set ReplaceInventoryItemIDWithPartNumber to true

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SalesRepresentativeReference>DGROSS</SalesRepresentativeReference>
    <UsualSalesAccountReference>40000-00</UsualSalesAccountReference>
    <OpenPurchaseOrderNumber />
    <ShipVia>None</ShipVia>
    <ResaleNumber />
    <PriceLevel>Price Level 1</PriceLevel>
    <UseEmailToDeliverForms>false</UseEmailToDeliverForms>
    <ReplaceInventoryItemIDWithUPC>false</ReplaceInventoryItemIDWithUPC>
    <ReplaceInventoryItemIDWithPartNumber>false</ReplaceInventoryItemIDWithPartNumber>
  </Customer>
</ArrayOfCustomer>
```

## Payment and Credit Fields
The below will let you specify the fields on the Payment & Credit tab in Sage.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Payment method | PaymentMethod | Check | string | 20 | Optional |
| Cash account | CashAccountReference | 10200-00 | string | 15 | Optional |
| Terms and Credit Option | Terms/PaymentTimeFrame* | DueInNumberOfDays | enum | - | Optional |
| Net due / Due on | Terms/DueDays* | 30 | int | - | Optional |
| Use discounts | UseDiscounts | true | bool | - | Optional |
| Discount in day | DiscountDays | 10 | int | - | Optional |
| Discount percent | DiscountPercent | 2.00 | decimal | - | Optional |
| Charge finance charges | ChargeInterest | true | bool | - | Optional |
| Credit limit | CreditLimit | 50000.00 | decimal | - | Optional |
| Credit status | CreditStatus* | NotifyOverLimit  | enum | - | Optional |

*   Terms/PaymentTimeFrame* - can be COD, Prepaid, DueInNumberOfDays, DueOnDayOfNextMonth or DueAtEndOfNextMonth
*   Terms/DueDays* - Sage field is only shown when using DueInNumberOfDays or DueOnDayOfNextMonth options from above, and wording changes depending on which
*   CreditStatus* - can be NoLimit, NotifyOverLimit, Notify, HoldoverLimit or Hold

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <PaymentMethod>Check</PaymentMethod>
    <CashAccountReference>10200-00</CashAccountReference>
      <Terms>
      <PaymentTimeFrame>DueInNumberOfDays</PaymentTimeFrame>
      <DueDays>30</DueDays>
      <UseDiscounts>true</UseDiscounts>
      <DiscountDays>10</DiscountDays>
      <DiscountPercent>2.00</DiscountPercent>
      <ChargeInterest>true</ChargeInterest>
      <CreditLimit>50000.00</CreditLimit>
    </Terms>
    <CreditStatus>NotifyOverLimit</CreditStatus>
  </Customer>
</ArrayOfCustomer>
```