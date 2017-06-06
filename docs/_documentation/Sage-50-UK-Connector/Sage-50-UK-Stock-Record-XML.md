---
slug: sage-50-uk-stock-record-xml
title: Sage 50 UK Stock Record XML
---
Import Products allows you to create and update products within Sage 50.

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
      <Publish>true</Publish>
      <TaxCode>1</TaxCode>
      <UnitOfSale>Each</UnitOfSale>
    </Product>
  </Products>
</Company>
```

## Details - Product Details  

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Product Code | Sku | PROD001  | string  | 30  | Required |
| Description | Name | Test Product  | string  | 60  | Optional  |
| Category  | GroupCode  | 1 | int  | 2 | Optional  |
| IntraStart Com. Code  | IntrastatCommodityCode  | 71162019  | string  | 8  | Optional  |
| Com. Code Description  | CommodityCode  | Necklaces  | string  | 30  | Optional  |
| Barcode  | Barcode  | 9789862410035  | string  | 60  | Optional  |
| Item Type  | ItemType*  | Stock | enum  | -  | Optional  |
| Location  | Location  | Warehouse  | string  | 16  | Optional  |
| Weight  | UnitWeight  | 12  | double  | -  | Optional  |

*   ItemType* - can be either Stock, NonStock or Service

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <Sku>PROD001</Sku>
      <Name>Test Product</Name>
      <GroupCode>1</GroupCode>
      <IntrastatCommodityCode>71162019</IntrastatCommodityCode>
      <CommodityCode>Necklaces</CommodityCode>
      <Barcode>9789862410035</Barcode>
      <ItemType>Stock</ItemType>
      <Location>Warehouse</Location>
      <UnitWeight>12</UnitWeight>
    </Product>
  </Products>
</Company>
```

## Details - Defaults  
| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Sales Nominal Code | NominalCode | 4000 | string  | 8 | Optional |
| Purchase Nominal Code | PurchaseNominalCode | 5001 | string  | 8  | Optional  |
| Supplier A/C | SupplierAccountRef | SUP001 | string  | 8 | Optional  |
| Tax Code  | TaxCode | 1 | int | 2  | Optional  |
| Part No. | SupplierPartNo  | 123 | string  | 16 | Optional  |
| Department | Department | 1 | int | 2  | Optional  |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <NominalCode>4000</NominalCode>
      <PurchaseNominalCode>5001</PurchaseNominalCode>
      <SupplierAccountRef>SUP001</SupplierAccountRef>
      <TaxCode>1</TaxCode>
      <SupplierPartNo>123</SupplierPartNo>
      <Department>1</Department>
    </Product>
  </Products>
</Company>
```

## Details - Status

When creating a new product you can optionally provide the QtyInStock which will create an opening balance adjustment in stock transaction.  The in stock quantity is not updated for existing products, to adjust stock levels of existing products see [Importing Stock Transactions into Sage 50 UK](importing-stock-transactions-into-sage-50-uk).

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| In Stock | QtyInStock | 10 | double | - | Optional |
| Re-order Qty | ReorderQty | 10 | double | -  | Optional  |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <QtyInStock>10</QtyInStock>
      <ReorderQty>10</ReorderQty>
    </Product>
  </Products>
</Company>
```

## Details - Ordering  

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Last Cost Price (Standard) | LastCostPrice | 5 | double | - | Optional |
| Last Cost Price (Discounted) | LastCostPriceDiscounted | 2 | double | -  | Optional  |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <LastCostPrice>5</LastCostPrice>
      <LastCostPriceDiscounted>2</LastCostPriceDiscounted>
    </Product>
  </Products>
</Company>
```

## Details - Sales Price  

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Price | SalePrice | 100 | double | - | Optional |
| Unit of Sale | UnitOfSale | Each | string | 8  | Optional  |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <SalePrice>100</SalePrice>
      <UnitOfSale>Each</UnitOfSale>
    </Product>
  </Products>
</Company>
```

## Discount  
You can import quantity break discounts into the discounts tables A, B, C, D and E.  Each table allows up to 10 quantity levels.  The levels are defined from the order of the product quantity breaks in the XML file.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Discount Table | Reference | A | string | 1 | Optional |
| Quantity  | Quantity  | 600  | double  | -  | Optional  |
| Discount % | DiscountPercentage | 50 | double | -  | Optional  |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <ProductQtyBreaks>
        <ProductQtyBreak>
          <Reference>A</Reference>
          <Quantity>600</Quantity>
          <DiscountPercentage>50</DiscountPercentage>
        </ProductQtyBreak>
        <ProductQtyBreak>
          <Reference>A</Reference>
          <Quantity>1200</Quantity>
          <DiscountPercentage>58.57</DiscountPercentage>
        </ProductQtyBreak>
        <ProductQtyBreak>
          <Reference>B</Reference>
          <Quantity>600</Quantity>
          <DiscountPercentage>45.71</DiscountPercentage>
        </ProductQtyBreak>
        <ProductQtyBreak>
          <Reference>C</Reference>
          <Quantity>1200</Quantity>
          <DiscountPercentage>17.14</DiscountPercentage>
        </ProductQtyBreak>
      </ProductQtyBreaks>
    </Product>
  </Products>
</Company>
```

## Web  

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Description | Description | Sample product | string | 60 | Optional |
| Details | LongDescription | A new sample product | string | 1023 | Optional  |
| Publish to Web  | Publish  | true  | bool  | -  | Optional  |
| Special Offer  | SpecialOffer  | false  | bool  | -  | Optional  |
| Category A | Custom1  | Blue  | string  | 60  | Optional   |
| Category B | Custom2  | Large  | string  | 60  | Optional   |
| Category C | Custom3  | Tee  | string  | 60  | Optional   |

```xml
<?xml version="1.0"?>
<Company>
  <Products>
    <Product>
      <Description>Sample product</Description>
      <LongDescription>A new sample product</LongDescription>
      <Publish>true</Publish>
      <SpecialOffer>false</SpecialOffer>
      <Custom1>Blue</Custom1>
      <Custom2>Large</Custom2>
      <Custom3>Tee</Custom3>
    </Product>
  </Products>
</Company>
```