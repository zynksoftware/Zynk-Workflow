---
slug: xero-item-xml
title: Xero Item XML
---
The Upsert Items task allows you to create new and update existing inventory items in Xero.  

Any Xero fields not documented below are not supported with our imports. Examples of where in the XML the fields should appear are shown in the samples below. 

Sample import file for creating or updating an item:

```xml
<?xml version="1.0"?>
<ArrayOfXeroItem>
  <XeroItem>
    <ExternalId>7814</ExternalId>
    <Code>PROD001</Code>
    <Name>A4 Paper</Name>
    <SalesDetails>
      <UnitPrice>4.00</UnitPrice>
      <AccountCode>200</AccountCode>
    </SalesDetails>
  </XeroItem>
</ArrayOfXeroItem>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the XML schema is used below as a reference of where fields should be in the object model.

## Matching Items
Any of the following fields can be used to match the items provided in the XML to existing items in Xero. At least one should be provided, to prevent items being duplicated in Xero.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Item ID | Id | cea98f0f-af1a-4b23-ac1b-9584ba014dcb | guid | 255 | Optional |
| - | ExternalId | 7814 | string | 255 | Optional | Zynk stores a mapping between Xero's item ID and the ExternalId, and will use this to look up the item ID. |
| Item Code | Code | PROD001 | string | 50 | Required |

```xml
<?xml version="1.0"?>
<ArrayOfXeroItem>
  <XeroItem>
    <Id>cea98f0f-af1a-4b23-ac1b-9584ba014dcb</Id>
    <ExternalId>7814</ExternalId>
    <Code>PROD001</Code>
  </XeroItem>
</ArrayOfXeroItem>
```

## Item Header
The following fields can be set in the item header section.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Item Code | Code | PROD001 | string | 50 | Required |
| Item Name | Name | A4 Paper | string | 50 | Optional |
| Inventory Asset Account | InventoryAssetAccountCode | 630 | string | 10 | Dependant | Required for tracked inventory items. Setting this field will tick the 'I track this item' check box. You must also provide the COGSAccountCode in the purchase details section when specifying this field. |

```xml
<?xml version="1.0"?>
<ArrayOfXeroItem>
  <XeroItem>
    <Code>PROD001</Code>
    <Name>A4 Paper</Name>
    <InventoryAssetAccountCode>630</InventoryAssetAccountCode>
  </XeroItem>
</ArrayOfXeroItem>
```

## Purchase Details
The following fields can be set in the purchase details section.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Unit Price | PurchaseDetails/UnitPrice | 2.00 | decimal | - | Optional |
| Cost of Goods Sold Account | PurchaseDetails/COGSAccountCode | 300 | string | 10 | Dependant | Required for tracked inventory items. |
| Tax Rate | PurchaseDetails/TaxType | INPUT2 | string | 10 | Optional | Will be set to the default tax rate associated with the selected account if not specified. |
| Purchases Description | PurchaseDescription | 1000 sheets of A4 paper | string | 4000 | Optional |

```xml
<?xml version="1.0"?>
<ArrayOfXeroItem>
  <XeroItem>
    <PurchaseDetails>
      <UnitPrice>2.00</UnitPrice>
      <COGSAccountCode>300</COGSAccountCode>
      <TaxType>INPUT2</TaxType>
    </PurchaseDetails>
    <PurchaseDescription>1000 sheets of A4 paper</PurchaseDescription>
  </XeroItem>
</ArrayOfXeroItem>
```

## Sales Details
The following fields can be set in the sales details section.

| Xero Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Unit Price | SalesDetails/UnitPrice | 4.00 | decimal | - | Optional |
| Sales Account | SalesDetails/AccountCode | 200 | string | 10 | Optional |
| Tax Rate | SalesDetails/TaxType | OUTPUT2 | string | 10 | Optional | Will be set to the default tax rate associated with the selected account if not specified. |
| Purchases Description | Description | 1000 sheets of A4 paper | string | 4000 | Optional |

```xml
<?xml version="1.0"?>
<ArrayOfXeroItem>
  <XeroItem>
    <SalesDetails>
      <UnitPrice>4.00</UnitPrice>
      <AccountCode>200</AccountCode>
      <TaxType>OUTPUT2</TaxType>
    </SalesDetails>
    <Description>1000 sheets of A4 paper</Description>
  </XeroItem>
</ArrayOfXeroItem>
```