---
slug: quickbooks-online-credit-memo-xml
title: Quickbooks Online Credit Memo XML
---
The Upload Credit Memos task allows you to create and update credit memos in QuickBooks. Any fields not documented below are not currently supported by our upload.

Sample import file for creating a basic credit memo:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCreditMemo>
    <ExternalId>7440</ExternalId>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <AutoDocNumber>true</AutoDocNumber>
      <Line>
        <Amount>50</Amount>
        <DetailType>SalesItemLineDetail</DetailType>
        <SalesItemLineDetail>
          <ItemRef name="Catering"></ItemRef>
          <UnitPrice>50</UnitPrice>
          <Qty>1</Qty>
          <TaxCodeRef name="20.0% S"></TaxCodeRef>
        </SalesItemLineDetail>
      </Line>
      <CustomerRef name="Zynk Software"></CustomerRef>
    </Data>
  </RecordOfCreditMemo>
</ArrayOfCreditMemo>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a credit memo. The whole structure from the root element down is shown in the samples below as a reference of where elements should appear in the object model.

## Credit Details

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Optional | Used for matching to existing credit memos. |
| ExternalId | - | 7440 | string | 255 | Optional | Used for matching to existing credit memos, and duplicate prevention. The value provided will be stored in Zynk's truth table, and used to lookup the Id of the credit memo. |
| DocNumber | Credit Note No. | 1001 | string | 21 | Dependant | Used for matching to existing credit memos. Can be auto generated when creating new credit memos, by setting AutoDocNumber to true (requires custom transaction numbers to be disabled in QuickBooks). |
| AutoDocNumber | - | false | boolean | - | Optional | Set to true to generate a DocNumber automatically if not specified in the XML. AutoDocNumber will default to false if not specified. |
| TxnDate | Credit Note Date | 2016-07-15 | date | - | Optional | Will default to the current date if not provided. |
| CustomerRef | Customer | 1 | integer | - | Required | If you don't know the customer ID, you can specify their name using the name attribute, and the task will perform a lookup. |
| DepartmentRef | Department | 1 | integer | - | Optional | Can only be set if department tracking is enabled in QuickBooks. If you don't know the department ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| ExchangeRate | Exchange Rate | 1.345 | decimal | - | Optional | Defaults to 1 if not specified. Can only be set if multi currency is enabled in QuickBooks. |
| PrivateNote | Memo | Example memo | string | 4000 | Optional |
| CustomerMemo | Message displayed on credit note | Example memo | string | 1000 | Optional |
| BillAddr | Billing Address | - | - | - | Optional | Will default to the customer's default bill-to address if not specified. |
| BillAddr > Line 1 | Billing Address | Zynk Software | string | 500 | Optional |
| BillAddr > Line 2 | Billing Address | Nelson House | string | 500 | Optional |
| BillAddr > Line 3 | Billing Address | Jesmond | string | 500 | Optional |
| BillAddr > Line 4 | Billing Address | string | 500 | Optional |
| BillAddr > Line 5 | Billing Address | string | 500 | Optional |
| BillAddr > City | Billing Address | Newcastle | string | 255 | Optional |
| BillAddr > Country | Billing Address | England | string | 255 | Optional |
| BillAddr > CountrySubDivisionCode | Billing Address | Tyne & Wear | string | 255 | Optional |
| BillAddr > PostalCode | Billing Address | NE2 3AE | string | 31 | Optional |
| ShipAddr | Shipping Address |  - | - | - | Optional | Will default to the customer's default ship-to address if not specified. |
| ShipAddr > Line 1 | Shipping Address | Zynk Software | string | 500 | Optional |
| ShipAddr > Line 2 | Shipping Address | Nelson House | string | 500 | Optional |
| ShipAddr > Line 3 | Shipping Address | Jesmond | string | 500 | Optional |
| ShipAddr > Line 4 | Shipping Address | string | 500 | Optional |
| ShipAddr > Line 5 | Shipping Address | string | 500 | Optional |
| ShipAddr > City | Shipping Address | Newcastle | string | 255 | Optional |
| ShipAddr > Country | Shipping Address | England | string | 255 | Optional |
| ShipAddr > CountrySubDivisionCode | Shipping Address | Tyne & Wear | string | 255 | Optional |
| ShipAddr > PostalCode | Shipping Address | NE2 3AE | string | 31 | Optional |
| SalesTermRef | Terms | 1 | integer | - | Optional | If you don't know the sales term ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| GlobalTaxCalculation | Amounts are | TaxExcluded | enum | - | Optional | Allowed values are TaxExcluded, TaxInclusive and NotApplicable. |
| ApplyTaxAfterDiscount | - | false | boolean | -| Optional| Only applicable to US version of QuickBooks. Defaults to false |
| PrintStatus | - | NeedToPrint | enum | - | Optional | Allowed values are NotSet, NeedToPrint and PrintComplete. Defaults to NotSet if not provided. |
| EmailStatus | - | NeedToSend | enum | - | Optional | Allowed values are NotSet, NeedToSend and EmailSent. Defaults to NotSet if not provided. |
| BillEmail > Address | Email | support@zynk.com | string | 100 | Dependant | Must be provided if EmailStatus is set to NeedToSend. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCreditMemo>
    <ExternalId>7440</ExternalId>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Id>1234</Id>
      <DocNumber>1001</DocNumber>
      <AutoDocNumber>false</AutoDocNumber>
      <TxnDate>2016-07-15</TxnDate>
      <CustomerRef name="Zynk Software">1</CustomerRef>
      <DepartmentRef name="Sales">1</DepartmentRef>
      <ExchangeRate>1.345</ExchangeRate>
      <PrivateNote>Example memo</PrivateNote>
      <CustomerMemo>Example memo</CustomerMemo>
      <BillAddr>
        <Line1>Zynk Software</Line1>
        <Line2>Nelson House</Line2>
        <Line3>Jesmond</Line3>
        <Line4></Line4>
        <Line5></Line5>
        <City>Newcastle</City>
        <Country>England</Country>
        <CountrySubDivisionCode>Tyne & Wear</CountrySubDivisionCode>
        <PostalCode>NE2 3AE</PostalCode>
      </BillAddr>
      <ShipAddr>
        <Line1>Zynk Software</Line1>
        <Line2>Nelson House</Line2>
        <Line3>Jesmond</Line3>
        <Line4></Line4>
        <Line5></Line5>
        <City>Newcastle</City>
        <Country>England</Country>
        <CountrySubDivisionCode>Tyne & Wear</CountrySubDivisionCode>
        <PostalCode>NE2 3AE</PostalCode>
      </ShipAddr>
      <SalesTermRef name="Due on receipt">1</SalesTermRef>
      <GlobalTaxCalculation>TaxExcluded</GlobalTaxCalculation>
      <ApplyTaxAfterDiscount>false</ApplyTaxAfterDiscount>
      <PrintStatus>NeedToPrint</PrintStatus>
      <EmailStatus>NeedToSend</EmailStatus>
      <BillEmail>
        <Address>support@zynk.com</Address>
      </BillEmail>
    </Data>
  </RecordOfCreditMemo>
</ArrayOfCreditMemo>
```

## Credit Details - Items
There are several different types of item that can be added to a credit note, as shown below. The item type is specified by the DetailType element in the XML.

### Sales Item Line

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Dependant | Used for matching to existing line items. Required when updating an existing item line. |
| LineNum | - | 1 | integer | - | Optional | Specifies the position of the line. |
| Description | Description | Catering | string | 4000 | Optional |
| Amount | Amount | 50 | decimal | - | Required | The total amount for the line. |
| DetailType | - | SalesItemLineDetail | enum | - | Required | Set to SalesItemLineDetail for this item type. |
| SalesItemLineDetail > ItemRef | Product/Service | 1 | integer | - | Required | If you don't know the item ID, you can specify the SKU or name using the name attribute, and the task will perform a lookup. |
| SalesItemLineDetail > UnitPrice | Rate | 50 | decimal | - | Optional |
| SalesItemLineDetail > Qty | Qty | 1 | decimal | - | Required |
| SalesItemLineDetail > TaxCodeRef | Vat | 1 | integer | - | Optional | If you don't know the tax code ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| SalesItemLineDetail > ServiceDate | Service Date | 2016-07-15 | date | - | Optional | Can only be set if service dates are enabled in QuickBooks. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCreditMemo>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Line>
        <Id>1234</Id>
        <LineNum>1</LineNum>
        <Description>Catering</Description>
        <Amount>50</Amount>
        <DetailType>SalesItemLineDetail</DetailType>
        <SalesItemLineDetail>
          <ItemRef name="Catering">3</ItemRef>
          <UnitPrice>50</UnitPrice>
          <Qty>1</Qty>
          <TaxCodeRef name="20.0% S">3</TaxCodeRef>
          <ServiceDate>2016-07-15</ServiceDate>
        </SalesItemLineDetail>
      </Line>
    </Data>
  </RecordOfCreditMemo>
</ArrayOfCreditMemo>
```

### Group Item Line

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Dependant | Used for matching to existing line items. Required when updating an existing item line. |
| LineNum | - | 1 | integer | - | Optional | Specifies the position of the line. |
| Description | Description | Group | string | 4000 | Optional |
| DetailType | - | GroupLineDetail | enum | - | Required | Set to GroupLineDetail for this item type. |
| GroupLineDetail > GroupItemRef | Product/Service | 1 | integer | - | Required | If you don't know the group item ID, you can specify the SKU or name using the name attribute, and the task will perform a lookup. The chosen item must have the type 'Group'. |
| GroupLineDetail > UnitPrice | Rate | 50 | decimal | - | Optional |
| GroupLineDetail > Quantity | Qty | 1 | decimal | - | Required |
| GroupLineDetail > Line | Product/Service | - | Item | - | Required | The collection of items in the group. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCreditMemo>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Line>
        <Id>1234</Id>
        <LineNum>1</LineNum>
        <Description>A Bundle Product</Description>
        <DetailType>GroupLineDetail</DetailType>
        <GroupLineDetail>
          <GroupItemRef name="Bundle Product">22</GroupItemRef>
          <Quantity>1</Quantity>
          <Line>
            <Id>4</Id>
            <LineNum>2</LineNum>
            <Description>Catering -- food & beverage</Description>
            <Amount>0</Amount>
            <DetailType>SalesItemLineDetail</DetailType>
            <SalesItemLineDetail>
              <ItemRef name="Catering">3</ItemRef>
              <UnitPrice>0</UnitPrice>
              <Qty>1</Qty>
              <TaxCodeRef name="20.0% S">3</TaxCodeRef>
            </SalesItemLineDetail>
          </Line>
          <Line>
            <Id>5</Id>
            <LineNum>3</LineNum>
            <Description>Entertainment for the event</Description>
            <Amount>0</Amount>
            <DetailType>SalesItemLineDetail</DetailType>
            <SalesItemLineDetail>
              <ItemRef name="Entertainment">6</ItemRef>
              <UnitPrice>0</UnitPrice>
              <Qty>1</Qty>
              <TaxCodeRef name="20.0% S">3</TaxCodeRef>
            </SalesItemLineDetail>
          </Line>
        </GroupLineDetail>
      </Line>
    </Data>
  </RecordOfCreditMemo>
</ArrayOfCreditMemo>
```

### Description Only Item Line
The description only item is also used for setting inline subtotals.

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Dependant | Used for matching to existing line items. Required when updating an existing item line. |
| LineNum | - | 1 | integer | - | Optional | Specifies the position of the line. |
| Description | Description | An item | string | 4000 | Optional | To create a subtotal line, set this to 'Subtotal:'. QuickBooks will calculate the subtotal amount automatically. |
| Amount | Amount | 50 | decimal | - | Dependant | Not required when creating a subtotal line. |
| DetailType | - | DescriptionOnly | enum | - | Required | Set to DescriptionOnly for this item type. |
| GroupLineDetail > ServiceDate | Service Date | 2016-07-15 | date | - | Optional | Can only be set if service dates are enabled in QuickBooks. |
| GroupLineDetail > TaxCodeRef | Vat | 1 | integer | - | Optional | If you don't know the tax code ID, you can specify the name using the name attribute, and the task will perform a lookup. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCreditMemo>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Line>
        <Id>1234</Id>
        <LineNum>1</LineNum>
        <Description>An item</Description>
        <Amount>50</Amount>
        <DetailType>DescriptionOnly</DetailType>
        <DescriptionLineDetail>
          <ServiceDate>2016-07-15</ServiceDate>
          <TaxCodeRef name="20.0% S">3</TaxCodeRef>
        </DescriptionLineDetail>
      </Line>
      <!-- Inline subtotal -->
      <Line>
        <Id>2</Id>
        <LineNum>2</LineNum>
        <Description>Subtotal:</Description>
        <DetailType>DescriptionOnly</DetailType>
        <DescriptionLineDetail />
      </Line>
    </Data>
  </RecordOfCreditMemo>
</ArrayOfCreditMemo>
```

### Discount Line
Specifies a discount to apply to the whole transaction. Discount Lines can only be added if discounts are enabled in QuickBooks.

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Amount | Amount | 10.5 | decimal | - | Required | The total amount for the line. |
| DetailType | - | DiscountLineDetail | enum | - | Required | Set to DiscountLineDetail for this item type. |
| DiscountLineDetail > PercentBased | Discount percent / Discount value | false | bool | - | Required | Set to true if the discount is a percentage discount, or false if it is a discount amount. |
| DiscountLineDetail > DiscountPercent | Rate | 10.5 | decimal | - | Optional |
| DiscountLineDetail > DiscountAccountRef | - | 1 | integer | - | Optional | If you don't know the account ID, you can specify the name using the name attribute, and the task will perform a lookup. The chosen accountmust have the Type 'Income' and Sub Type 'DiscountsRefundsGiven'. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCreditMemo>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Line>
        <Amount>10.5</Amount>
        <DetailType>DiscountLineDetail</DetailType>
        <DiscountLineDetail>
          <PercentBased>false</PercentBased>
          <DiscountPercent>10.5</DiscountPercent>
          <DiscountAccountRef name="Discounts given">1</DiscountAccountRef>
        </DiscountLineDetail>
      </Line>
    </Data>
  </RecordOfCreditMemo>
</ArrayOfCreditMemo>
```

## Custom Fields
QuickBooks supports up to 3 custom fields, which can be set as described below. The custom field must already exist in QuickBooks, the task will not automatically create custom fields.

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| DefinitionId | Name | 1 | integer | - | Dependant | This is the number of the custom field, used for matching. Will be either 1, 2 or 3\. Required if Name is not specified. |
| Name | Name | Sales Rep | string | 15 | Dependant | The name of the custom field, used for matching. Required if DefinitionId is not specified. |
| StringValue | Value | John Smith | string | 31 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCreditMemo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCreditMemo>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <CustomField>
        <DefinitionId>1</DefinitionId>
        <Name>Sales Rep</Name>
        <StringValue>John Smith</StringValue>
      </CustomField>
    </Data>
  </RecordOfCreditMemo>
</ArrayOfCreditMemo>
```