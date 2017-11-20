---
slug: sage-200-stock-record-xml
title: Sage 200 Stock Record XML
---
Import Stock Records allows you to create and update products within Sage 200.  

Any fields not documented below are not supported with our imports.  

Sample import file for creating a basic product:

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <Sku>PROD001</Sku>
      <Name>Test Product</Name>
      <SalePrice>100</SalePrice>
      <TaxCode>1</TaxCode>
      <UnitOfSale>Each</UnitOfSale>
    </Product>
  </Products>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the Company schema is used below as a reference of where fields should be in the XML.

## Details
The information below can be specified on the Details tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Code | Sku | PROD001  | string  | 30  | Required |
| Name | Name | Test Product  | string  | 60  | Optional  |
| Product Group | GroupCode | TESTGROUP | string | 20 | Optional | If the product group does not already exist, it will be created automatically. If no group code is provided, it will default to the setting at the task level. |
| Product Group - Description  | GroupName | Test Group | string | 60 | Optional | Only used when creating a new product group. If it is not provided, the description will default to the value of the GroupCode. |
| Product Type | ItemType | Stock | string | 60 | Optional | If the product group already exists, the ItemType provided must match that of the product group. If an ItemType is not provided, it will default to the type associated with the product group. When creating a new product group, its type will be set based on the ItemType provided. If it is not provided, it will default to Stock. The following types are supported: Stock, NonStock and Miscellaneous.|
| Current Status | Status | 1 | string | - | Optional | Set to 1 for 'Active', or 0 for 'Inactive'. |
| Price | SalePrice | 100 | double | - | Optional |
| Stock unit | UnitOfSale | Each | string | 20 | Optional | The 'Use multiple units' option in the Product Group must be enabled to set the UnitOfSale. |
| Tax Rate | TaxCode | 1 | int | - | Optional |
| Manufacturer | Manufacturer | Test Company | string | 40 | Optional |
| Part No | ManufacturerPartNo | 1234 | string | 40 | Optional |
| Average Buying Price | StandardCostPrice | 60 | double | - | Optional |
| Item Description | Description | This is a test product | string | - | Optional |
| Use Item Description On Orders And Invoices | UseDescriptionOnDocs | false | bool | - | Optional |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <Sku>PROD001</Sku>
      <Name>Test Product</Name>
      <GroupCode>TESTGROUP</GroupCode>
      <GroupName>Test Group</GroupName>
      <ItemType>Stock</ItemType>
      <Status>1</Status>
      <SalePrice>100</SalePrice>
      <UnitOfSale>Each</UnitOfSale>
      <TaxCode>1</TaxCode>
      <Manufacturer>Test Company</Manufacturer>
      <ManufacturerPartNo>1234</ManufacturerPartNo>
      <StandardCostPrice>60</StandardCostPrice>
      <Description>This is a test product</Description>
      <UseDescriptionOnDocs>false</UseDescriptionOnDocs>
    </Product>
  </Products>
</Company>
```

## Analysis
The information below can be specified on the Analysis tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Search Category | SearchCategories/SearchCategory/Name | Sync with Website | string | 40 | Optional |
| Search Value | SearchCategories/SearchCategory/Value | true | string | 40 | Optional |
| Default nominal codes - Stock - A/C Ref | StockNominal/Code | 13103 | int | -  | Optional  |
| Default nominal codes - Stock - CC | StockNominal/CostCentre | string | 3 | Optional A StockNominal/Code must be provided if specifying CostCentre |
| Default nominal codes - Stock - Dept | StockNominal/Department | string | 3 | Optional A StockNominal/Code must be provided if specifying Department |
| Default nominal codes - Revenue - A/C Ref | RevenueNominal/Code | 31100 | int | -  | Optional  |
| Default nominal codes - Revenue - CC | RevenueNominal/CostCentre | SAL | string | 3 | Optional A RevenueNominal/Code must be provided if specifying CostCentre |
| Default nominal codes - Revenue - Dept | RevenueNominal/Department | VAL | string | 3 | Optional A RevenueNominal/Code must be provided if specifying Department |
| Default nominal codes - Accrued receipts - A/C Ref | AccruedReceiptsNominal/Code | 29100 | int | -  | Optional  |
| Default nominal codes - Accrued receipts - CC | AccruedReceiptsNominal/CostCentre | string | 3 | Optional A AccruedReceiptsNominal/Code must be provided if specifying CostCentre |
| Default nominal codes - Accrued receipts - Dept | AccruedReceiptsNominal/Department | string | 3 | Optional A AccruedReceiptsNominal/Code must be provided if specifying Department |
| Default nominal codes - Issues - A/C Ref | IssuesNominal/Code | 44100 | int | -  | Optional  |
| Default nominal codes - Issues - CC | IssuesNominal/CostCentre | SAL | string | 3 | Optional A IssuesNominal/Code must be provided if specifying CostCentre |
| Default nominal codes - Issues - Dept | IssuesNominal/Department | VAL | string | 3 | Optional A IssuesNominal/Code must be provided if specifying Department |
| Weight  | UnitWeight  | 12  | double  | -  | Optional  |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <SearchCategories>
        <SearchCategory>
          <Name>Sync with Website</Name>
          <Value>true</Value>
        </SearchCategory>
      </SearchCategories>
      <StockNominal>
        <Code>13103</Code>
        <CostCentre/>
        <Department/>
      </StockNominal>
      <RevenueNominal>
        <Code>31100</Code>
        <CostCentre>SAL</CostCentre>
        <Department>VAL</Department>
      </RevenueNominal>
      <AccruedReceiptsNominal>
        <Code>29100</Code>
        <CostCentre/>
        <Department/>
      </AccruedReceiptsNominal>
      <IssuesNominal>
        <Code>44100</Code>
        <CostCentre>SAL</CostCentre>
        <Department>VAL</Department>
      </IssuesNominal>
      <UnitWeight>12</UnitWeight>
    </Product>
  </Products>
</Company>
```

## Suppliers
The information below can be specified on the Suppliers tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| A/C Ref | AccountReference | SUP001 | string | 8 | Required |
| Supplier stock code | SupplierStockCode | S-PROD001 | string | 40 | Required |
| Lead Time | LeadTime | 3 | short | - | Optional |
| Lead Time Unit | LeadTimeUnit | EnumTimeUnitDay | enum | - | Optional | Can be either EnumTimeUnitDay, EnumTimeUnitWeek, EnumTimeUnitMonth, or EnumTimeUnitYear. |
| Usual Order Quantity | UsualOrderQuantity | 1 | decimal | - | Optional |
| Minimum Order Quantity | MinimumOrderQuantity | 1 | decimal | - | Optional |
| Supplier List Price | ListPrice | 60 | decimal | - | Optional |
| List Price Updated | DateListPriceChanged | 2014-01-01T00:00:00 | datetime | - | Optional |
| List Price Expiry | ListPriceExpiryDate | 2015-01-01T00:00:00 | datetime | - | Optional |
| Price Source | PricingSource | LastBuyingPrice | enum | - | Optional | Can be either LastBuyingPrice or ListPrice. |
| Pref | Preferred | true | bool | - | Optional |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <ProductSuppliers>
        <ProductSupplier>
          <AccountReference>SUP001</AccountReference>
          <SupplierStockCode>S-PROD001</SupplierStockCode>
          <LeadTime>3</LeadTime>
          <LeadTimeUnit>EnumTimeUnitDay</LeadTimeUnit>
          <UsualOrderQuantity>1</UsualOrderQuantity>
          <MinimumOrderQuantity>1</MinimumOrderQuantity>
          <ListPrice>60</ListPrice>
          <DateListPriceChanged>2014-01-01T00:00:00</DateListPriceChanged>
          <ListPriceExpiryDate>2015-01-01T00:00:00</ListPriceExpiryDate>
          <PricingSource>LastBuyingPrice</PricingSource>
          <Preferred>true</Preferred>
        </ProductSupplier>
      </ProductSuppliers>
    </Product>
  </Products>
</Company>
```

## Locations
The information below can be specified on the Locations tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Re-order | ReorderLvl | 10 | double | - | Optional | This will set the Re-order level on the first warehouse in the list.|

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <ReorderLvl>10</ReorderLvl>
    </Product>
  </Products>
</Company>
```

## Comments
The information below can be specified on the Comments tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Default Comment for Picking List | DefaultPickingListComment | Picking list comment | string | 160 | Optional |
| Default Comment for Despatch Note | DefaultDespatchNoteComment | Despatch note comment | string | 160 | Optional |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <ProductSuppliers>
        <ProductSupplier>
          <DefaultPickingListComment>Picking list comment</DefaultPickingListComment>
          <DefaultDespatchNoteComment>Despatch note comment</DefaultDespatchNoteComment>
        </ProductSupplier>
      </ProductSuppliers>
    </Product>
  </Products>
</Company>
```

## Stock Order Fulfilment
The information below can be specified on the Stock Records > Stock Order Fulfilment section in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Fulfilment Method | FulfilmentMethod | FromStock | enum | - | Optional | Can be set to FromStock, FromSupplier or DirectToCustomer. Defaults to FromStock. |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <FulfilmentMethod>FromStock</FulfilmentMethod>
    </Product>
  </Products>
</Company>
```
