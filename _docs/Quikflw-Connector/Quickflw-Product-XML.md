---
slug: quickflw-product-xml
title: Quickflw Product XML
---
The [Upload Products into Quickflw]() task allows you to create new and update existing products in Quikflw. The XML format required is provided below. Any fields not documented here are not supported within our imports to Quikflw.

## Product

| Quikflw Field | XML Field | Example | Field Type | Notes |
| --- | --- | --- | --- | --- |
| N/A | Id | 380c52b5-8f1a-4837-99ec-614716e8e456 | string | |
| Item Code | ProductCode | EXAMPLE-PRODUCT | string | |
| Description | Description | This is a test product. | string |
| Detailed Description | DetailedDescription | This example product is used for documentation. | string | |
| Category | Category | Test Products | string | |
| Type Unit | Unit | kgs | string | |
| Price | Price | 9.99 | double | |
| Cost | Cost | 0.99 | double | |
| Labour Name | LabourName | Test | string | |
| Labour Hours | LabourHours | 3 | double | |
| Labour Rate | LabourRate | 50 | double | |
| Use Price Breaks | UsePriceBreaks | false | bool | |

### Tax Codes
| Quikflw Field | XML Field | Example | Field Type |
| --- | --- | --- | --- | --- |
| Tax Code Sales | SalesTaxCode/Value | 20.0% S | string | | 
| Purchases Tax Code | PurchasesTaxCode/Value | No VAT | string | | 

#### Sales Tax Code
Quickflw supports tax codes. These to be setup by navigating to the settings cog on the top right and selecting 'Account Settings'.

```xml
<SalesTaxCode>
    <Value>20.0% S</Value>
</SalesTaxCode>
```

#### Purchases Tax Code

```xml
<PurchasesTaxCode>
    <Value>No VAT</Value>
</PurchasesTaxCode>
```

### Account Codes
Quickflw supports account codes. These to be setup by navigating to the settings cog on the top right and selecting 'Account Settings'.

| Quikflw Field | XML Field | Example | Field Type |
| --- | --- | --- | --- | --- |
| Sales Account Code | SalesAccountCode/Value | 1000 | string | | 
| Purchases Account Code | PurchasesAccountCode/Value | 1001 | string | | 

#### Sales Account Code
```xml
<SalesAccountCode>
    <Id>63444046-a6a8-4fcb-b097-3379d80dc73d</Id>
    <Value>1000</Value>
</SalesAccountCode>
```

#### Purchases Account Code
```xml
<PurchasesAccountCode>
    <Id>63444046-a6a8-4fcb-b097-3379d80dc73d</Id>
    <Value>1001</Value>
</PurchasesAccountCode>
```

### Custom Fields
Quickflw allows custom fields to be setup by navigating to the settings cog on the top right and selecting 'Item Settings'.
| Quikflw Field | XML Field | Example | Field Type |
| --- | --- | --- | --- | --- |
| Custom Field Label | CustomField/Label | Manufacturer | string | | 
| Custom Field Value | CustomField/Value | Zynk | string | | 

```xml 
<CustomFields>
    <CustomField>
        <Label>Custom Field</Label>
        <Value>Custom Field Value</Value>
    </CustomField>
</CustomFields>
```
#### Minimal Product Upload
The following fields are required by Quikflw to upload products:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Products xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <ProductCode>TEST-PRODUCT</ProductCode>
    <Description>This is a test product.</Description>
  </Product>
</Products>
```

#### Sample Product Upload
```xml
<?xml version="1.0" encoding="utf-8"?>
<Products xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <ProductCode>EXAMPLE-PRODUCT</ProductCode>
    <Description>This is a test product.</Description>
    <DetailedDescription>This example product is used for documentation.</DetailedDescription>
    <Category>Test Category</Category>
    <Unit>kgs</Unit>
    <Price>100</Price>
    <Cost>10</Cost>
    <LabourName>Test Labour</LabourName>
    <LabourHours>10</LabourHours>
    <LabourRate>1</LabourRate>
    <UsePriceBreaks>false</UsePriceBreaks>
    <SalesTaxCode>
        <Id>ac3eb80c-a83d-4b64-8516-549a97813b8e</Id>
        <Value>20.0% S</Value>
    </SalesTaxCode>
    <PurchasesTaxCode>
        <Id>63444046-a6a8-4fcb-b097-3379d80dc73d</Id>
        <Value>No VAT</Value>
    </PurchasesTaxCode>
    <SalesAccountCode>
        <Id>63444046-a6a8-4fcb-b097-3379d80dc73d</Id>
        <Value>1000</Value>
    </SalesAccountCode>
    <PurchasesAccountCode>
        <Id>63444046-a6a8-4fcb-b097-3379d80dc73d</Id>
        <Value>1001</Value>
    </PurchasesAccountCode>
    <CustomFields>
        <CustomField>
            <Label>Custom Field 1</Label>
            <Value>TEST CUSTOM FIELD</Value>
        </CustomField>
    </CustomFields>
  </Product>
</Products>
```
