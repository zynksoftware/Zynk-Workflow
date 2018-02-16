---
slug: quickbooks-online-purchase-order-xml
title: Quickbooks Online Purchase Order XML
---
The Upload Purchase Orders task allows you to create and update purchase orders in QuickBooks. Any fields not documented below are not currently supported by our upload.

Sample import file for creating a basic purchase order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPurchaseOrder>
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
      <APAccountRef name="Creditors"></APAccountRef>
      <VendorRef name="Zynk Software Vendor"></VendorRef>
    </Data>
  </RecordOfPurchaseOrder>
</ArrayOfPurchaseOrder>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a purchase order. The whole structure from the root element down is shown in the samples below as a reference of where elements should appear in the object model.

## Purchase Order Details

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Optional | Used for matching to existing purchase orders. |
| ExternalId | - | 7440 | string | 255 | Optional | Used for matching to existing purchase orders, and duplicate prevention. The value provided will be stored in Zynk's truth table, and used to lookup the Id of the purchase order. |
| DocNumber | Purchase Order No. | 1001 | string | 21 | Dependant | Used for matching to existing purchase orders. Can be auto generated when creating new purchase orders, by setting AutoDocNumber to true (requires custom transaction numbers to be disabled in QuickBooks). |
| AutoDocNumber | - | false | boolean | - | Optional | Set to true to generate a DocNumber automatically if not specified in the XML. AutoDocNumber will default to false if not specified. |
| TxnDate | Purchase Order Date | 2016-07-15 | date | - | Optional | Will default to the current date if not provided. |
| VendorRef | Supplier | 1 | integer | - | Required | If you don't know the supplier ID, you can specify their name using the name attribute, and the task will perform a lookup. |
| DepartmentRef | Department | 1 | integer | - | Optional | Can only be set if department tracking is enabled in QuickBooks. If you don't know the department ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| ExchangeRate| Exchange Rate| 1.345| decimal| -| Optional| Defaults to 1 if not specified. Can only be set if multi currency is enabled in QuickBooks.|
| PrivateNote | Memo | Example memo | string | 4000 | Optional |
| Memo | Your Message To Supplier | Example memo | string | 1000 | Optional |
| VendorAddr | Mailing Address| - | - | - | Optional | Will default to the supplier's default address if not specified. |
| VendorAddr > Line 1 | Mailing Address | Zynk Software | string | 500 | Optional |
| VendorAddr > Line 2 | Mailing Address | Nelson House | string | 500 | Optional |
| VendorAddr > Line 3 | Mailing Address | Jesmond | string | 500 | Optional |
| VendorAddr > Line 4 | Mailing Address | string | 500 | Optional |
| VendorAddr > Line 5 | Mailing Address | string | 500 | Optional |
| VendorAddr > City | Mailing Address | Newcastle | string | 255 | Optional |
| VendorAddr > Country | Mailing Address | England | string | 255 | Optional |
| VendorAddr > CountrySubDivisionCode | Mailing Address | Tyne & Wear | string | 255 | Optional |
| VendorAddr > PostalCode | Mailing Address | NE2 3AE | string | 31 | Optional |
| ShipAddr | Shipping Address |  - | - | - | Optional | Will default to your companies default address if not specified. |
| ShipAddr > Line 1 | Shipping Address | Zynk Software | string | 500 | Optional |
| ShipAddr > Line 2 | Shipping Address | Nelson House | string | 500 | Optional |
| ShipAddr > Line 3 | Shipping Address | Jesmond | string | 500 | Optional |
| ShipAddr > Line 4 | Shipping Address | string | 500 | Optional |
| ShipAddr > Line 5 | Shipping Address | string | 500 | Optional |
| ShipAddr > City | Shipping Address | Newcastle | string | 255 | Optional |
| ShipAddr > Country | Shipping Address | England | string | 255 | Optional |
| ShipAddr > CountrySubDivisionCode | Shipping Address | Tyne & Wear | string | 255 | Optional |
| ShipAddr > PostalCode | Shipping Address | NE2 3AE | string | 31 | Optional |
| APAccountRef | Account | 1 | integer | - | Required | If you don't know the account ID, you can specify the name using the name attribute, and the task will perform a lookup. The chosen account must have the classification 'Liability' and sub type 'Accounts Payable'. |
| SalesTermRef | Terms | 1 | integer | - | Optional | If you don't know the sales term ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| DueDate | Due Date | 2016-07-15 | date | - | Optional | Will be set based on the SalesTermRef of not specified. |
| GlobalTaxCalculation | Amounts are | TaxExcluded | enum | - | Optional | Allowed values are TaxExcluded, TaxInclusive and NotApplicable. |
| ShipMethodRef | Ship Via | 1 | integer | - | Optional | If you don't know the shipping method ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| POStatus | - | Open | enum | - | Optional | Allowed values are Open and Closed. Defaults to Open if not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPurchaseOrder>
    <ExternalId>7440</ExternalId>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Id>1234</Id>
      <DocNumber>1001</DocNumber>
      <AutoDocNumber>false</AutoDocNumber>
      <TxnDate>2016-07-15</TxnDate>
      <VendorRef name="Zynk Software Vendor">1</VendorRef>
      <DepartmentRef name="Sales">1</DepartmentRef>
      <ExchangeRate>1.345</ExchangeRate>
      <PrivateNote>Example memo</PrivateNote>
      <Memo>Example memo</Memo>
      <VendorAddr>
        <Line1>Zynk Software</Line1>
        <Line2>Nelson House</Line2>
        <Line3>Jesmond</Line3>
        <Line4></Line4>
        <Line5></Line5>
        <City>Newcastle</City>
        <Country>England</Country>
        <CountrySubDivisionCode>Tyne & Wear</CountrySubDivisionCode>
        <PostalCode>NE2 3AE</PostalCode>
      </VendorAddr>
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
      <DueDate>2016-07-15</DueDate>
      <GlobalTaxCalculation>TaxExcluded</GlobalTaxCalculation>
      <ShipMethodRef name="DHL">1</ShipMethodRef>
      <POStatus>Open</POStatus>
    </Data>
  </RecordOfPurchaseOrder>
</ArrayOfPurchaseOrder>
```

## Purchase Order Details - Items
There are two types of item that can be added to a purchase order, as shown below. The item type is specified by the DetailType element in the XML.


### Item Based Expense Line

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Dependant | Used for matching to existing line items. Required when updating an existing item line. |
| LineNum | - | 1 | integer | - | Optional | Specifies the position of the line. |
| Description| Description| Water bottles| string | 4000 | Optional |
| Amount | Amount | 661.71 | decimal | - | Required | The total amount for the line. |
| DetailType | - | ItemBasedExpenseLineDetail | enum | - | Required | Set to ItemBasedExpenseLineDetail for this item type. |
| ItemBasedExpenseLineDetail > ItemRef | Product/Service | 1 | integer | - | Optional | If you don't know the item ID, you can specify the SKU or name using the name attribute, and the task will perform a lookup. If an item ref is not provided, it is treated as documentation and the Amount will be ignored. |
| ItemBasedExpenseLineDetail > UnitPrice | Rate | 66.1717023 | decimal | - | Optional |
| ItemBasedExpenseLineDetail > MarkupInfo > PercentBased | - | true | boolean | - | Optional |
| ItemBasedExpenseLineDetail > MarkupInfo > Value | - | 40 | decimal | - | Optional |
| ItemBasedExpenseLineDetail > MarkupInfo > Percent | - | 80 | decimal | - | Optional |
| ItemBasedExpenseLineDetail > Qty | Qty | 10 | decimal | - | Required |
| ItemBasedExpenseLineDetail > TaxCodeRef | Vat | 13.24 | integer | - | Optional | If you don't know the tax code ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| ItemBasedExpenseLineDetail > CustomerRef | Customer | 1 | integer | - | Optional | If you don't know the customer ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| ItemBasedExpenseLineDetail > Billable Status | - |  Billable | enum | - | Optional | Allowed values are Billable, NotBillable and HasBeenBill. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPurchaseOrder>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Line>
        <Id>1234</Id>
        <LineNum>1</LineNum>
        <Description>Water bottles</Description>
        <Amount>661.71</Amount>
        <DetailType>ItemBasedExpenseLineDetail</DetailType>
        <ItemBasedExpenseLineDetail>
          <ItemRef name="Water Bottles"></ItemRef>
          <UnitPrice>66.1717023</UnitPrice>
          <MarkupInfo>
            <PercentBased>true</PercentBased>
            <Value>52.9373618</Value>
            <Percent>80</Percent>
          </MarkupInfo>
          <Qty>10</Qty>
          <TaxCodeRef name="20.0% S">1</TaxCodeRef>
          <CustomerRef name="Zynk Software">1</CustomerRef>
          <BillableStatus>Billable</BillableStatus>
        </ItemBasedExpenseLineDetail>
      </Line>
    </Data>
  </RecordOfPurchaseOrder>
</ArrayOfPurchaseOrder>
```

### Account Based Expense Line

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Dependant | Used for matching to existing line items. Required when updating an existing item line. |
| LineNum | - | 1 | integer | - | Optional | Specifies the position of the line. |
| Description | Description | Expense | string | 4000 | Optional |
| Amount | Amount | 200.00 | decimal | - | Required | The total amount for the line. |
| DetailType | - | AccountBasedExpenseLineDetail | enum | - | Required | Set to AccountBasedExpenseLineDetail for this item type. |
| AccountBasedExpenseLineDetail > AccountRef | Account | 1 | decimal | - | Required | If you don't know the account ID, you can specify the name using the name attribute, and the task will perform a lookup. The chosen account must have the type 'Expense'. |
| ItemBasedExpenseLineDetail > MarkupInfo > PercentBased | - | true | boolean | - | Optional |
| ItemBasedExpenseLineDetail > MarkupInfo > Value | - | 150.00 | decimal | - | Dependant | Required when PercentBased is set to false. |
| ItemBasedExpenseLineDetail > MarkupInfo > Percent | - | 75 | decimal | - | Dependant | Required when PercentBased is set to true. |
| ItemBasedExpenseLineDetail > TaxAmount | Vat | 40 | decimal | - | Optional |
| ItemBasedExpenseLineDetail > TaxCodeRef | Vat | 1 | integer | - | Optional | If you don't know the tax code ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| ItemBasedExpenseLineDetail > CustomerRef | Customer | 1 | integer | - | Optional | If you don't know the customer ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| ItemBasedExpenseLineDetail > Billable Status | - |  Billable | enum | - | Optional | Allowed values are Billable, NotBillable and HasBeenBill. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPurchaseOrder>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Line>
        <Id>1234</Id>
        <Description>Expense</Description>
        <Amount>200.00</Amount>
        <DetailType>AccountBasedExpenseLineDetail</DetailType>
        <AccountBasedExpenseLineDetail>
          <AccountRef name="Dues and Subscriptions">1</AccountRef>
          <TaxAmount>40</TaxAmount>
          <MarkupInfo>
            <PercentBased>true</PercentBased>
            <Value>150.00</Value>
            <Percent>75</Percent>
          </MarkupInfo>
          <TaxCodeRef name="20.0% S">1</TaxCodeRef>
          <CustomerRef name="Zynk Software">1</CustomerRef>
          <BillableStatus>Billable</BillableStatus>
        </AccountBasedExpenseLineDetail>
      </Line>
    </Data>
  </RecordOfPurchaseOrder>
</ArrayOfPurchaseOrder>
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
<ArrayOfPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPurchaseOrder>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <CustomField>
        <DefinitionId>1</DefinitionId>
        <Name>Sales Rep</Name>
        <StringValue>John Smith</StringValue>
      </CustomField>
    </Data>
  </RecordOfPurchaseOrder>
</ArrayOfPurchaseOrder>
```