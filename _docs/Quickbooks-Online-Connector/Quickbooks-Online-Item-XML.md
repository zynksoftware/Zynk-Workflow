---
slug: quickbooks-online-item-xml
title: Quickbooks Online Item XML
---
The Upload Items task allows you to create and update items in QuickBooks. Any fields not documented below are not currently supported by our upload.

Sample import file for creating a basic item:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfItem xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfItem>
    <ExternalId>PROD-1</ExternalId>
    <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
      <Name>Product 1</Name>
      <Sku>PROD-1</Sku>
      <Type>NonInventory</Type>
      <IncomeAccountRef name="Sales of Product Income"></IncomeAccountRef>
      <SalesTaxCodeRef name="20.0% S"></SalesTaxCodeRef>
      <PurchaseTaxCodeRef name="20.0% S"></PurchaseTaxCodeRef>
    </Data>
  </RecordOfItem>
</ArrayOfItem>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create an item. The whole structure from the root element down is shown in the samples below as a reference of where elements should appear in the object model.

## Item Details

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Optional | Used for matching to existing items. |
| ExternalId | - | 6492 | string | 255 | Optional | Used for matching to existing items. The value provided will be stored in Zynk's truth table, and used to lookup the Id of the item. |
| Name | Name | Name Badges | string | 100 | Required | Used for matching to existing items, if a Sku is not provided. |
| Sku | Item/Service Code | BADGE01 | string | - | Optional | Used for matching to existing items |
| Type | - | Inventory | enum | - | Required | Allowed values are Inventory, Service and NonInventory. |
| SubItem | Is Sub-Product/Service | true | boolean | - | Optional |
| ParentRef | Parent Product/Service | 1 | integer | - | Optional | If you don't know the item ID, you can specify the Sku or Name using the name attribute, and the task will perform a lookup. |
| QtyOnHand | Quantity On Hand | 45 | decimal | - | Dependant | Required for items of type 'Inventory'. |
| InvStartDate | As Of Date | 2016-07-15 | date | - | Dependant | Required for items of type 'Inventory'. When creating new items, this set the 'As Of Date' in QuickBooks. When updating an existing item, this sets the inventory adjustment date. |
| AssetAccountRef | Stock Asset Account | 1 | integer | - | Dependant | Required for items of type 'Inventory'. If you don't know the account ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| Description | Sales Information | Product info | string | 4000 | Optional |
| UnitPrice | Sales Price/Rate | 24.99 | decimal | - | Optional | Defaults to 0 if not specified. |
| IncomeAccountRef | Income Account | 1 | integer | - | Dependant | Required for items of type 'Inventory' and 'Service'. If you don't know the account ID, you can specify the name using the name attribute, and the task will perform a lookup. The chosen account must have the type 'Sales of Product Income'. |
| SalesTaxIncluded | Inclusive Of Tax | false | boolean | - | Optional | Defaults to false if not specified. |
| SalesTaxCodeRef | Tax | 1 | integer | - | Optional | If you don't know the tax code ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| PurchaseDesc | Purchasing Information | Purchase info | string | 1000 | Optional |
| PurchaseCost | Cost | 12.50 | decimal | - | Optional |
| ExpenseAccountRef | Expense Account | 1 | integer | - | Required | If you don't know the account ID, you can specify the name using the name attribute, and the task will perform a lookup. The chosen account must have the type 'Cost of Goods Sold'. |
| PurchaseTaxIncluded | Inclusive Of Purchase Tax | false | boolean | - | Optional | Defaults to false if not specified. |
| PurchaseTaxCodeRef | Purchase Tax | 1 | integer | - | Optional | If you don't know the tax code ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| Active | Active | true | boolean | - | Optional | Defaults to true if not specified. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfItem xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfItem>
    <ExternalId>6492</ExternalId>
    <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
      <Id>1234</Id>
      <Name>Name Badges</Name>
      <Sku>BADGE-01</Sku>
      <Type>Inventory</Type>
      <SubItem>true</SubItem>
      <ParentRef name="BADGE">1</ParentRef>
      <QtyOnHand>45</QtyOnHand>
      <InvStartDate>2016-07-15</InvStartDate>
      <AssetAccountRef name="Stock Asset">1</AssetAccountRef>
      <Description>Product info</Description>
      <UnitPrice>24.99</UnitPrice>
      <IncomeAccountRef name="Sales">1</IncomeAccountRef>
      <SalesTaxIncluded>false</SalesTaxIncluded>
      <SalesTaxCodeRef name="20.0% S">1</SalesTaxCodeRef>
      <PurchaseDesc>Purchase info</PurchaseDesc>
      <PurchaseCost>12.50</PurchaseCost>
      <ExpenseAccountRef name="Cost of Sales">1</ExpenseAccountRef>
      <PurchaseTaxIncluded>false</PurchaseTaxIncluded>
      <PurchaseTaxCodeRef name="20.0% S">1</PurchaseTaxCodeRef>
      <Active>true</Active>
    </Data>
  </RecordOfItem>
</ArrayOfItem>
```