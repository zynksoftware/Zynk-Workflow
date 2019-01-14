---
slug: quickflw-quotation-section-item-xml
title: Quickflw Quotation Section Item XML
---

## Quotation Section Item

| Quikflw Field | XML Field | Example |
| --- | ---| --- |
| - | Id | d3cef410-9819-49a8-b9e3-95bcc01fc065
| Item Code | ProductCode | TEST
| - | Information | [See Product XML](Quikflw-Product-XML)
| - | Unit | kgs
| Quantity | Quantity | 1
| - | SetupCost | 0
| - | VatPercentage | 20
| - | Markup | 0
| Discount % | DiscountPercentage | 5
| List Price | ListPrice | 100
| Sales Price | Price | 95
| - | ListCost | 0
| - | Cost | 0
| - | LabourName | Test Labour
| - | LabourHours | 10 
| - | LabourRate | 1
| - | LabourCostRate | 0
| - | LabourPrice | 10
| - | LabourCost | 0
| - | Margin | 100
| - | MarginPrice | 95
| - | Total | 105
| - | ImageUrl | /Product Images/NotFound.png
| - | IsKit | false
| - | IsKitItem | false
| - | IsComment | false
| Hide on Quote | HidePrices | false
| - | CanDelete | true
| - | HideOnPdf | false
| - | IsRequired | false
| Position | SortPos | 0
| Quotation -> Client Customization -> Allow Client to Customize Quotation | AllowClientToCustomize | false
| Tax Code | Value | 20.0% S
| - | PurchasesAccountCode | Purchases
| - | SalesAccountCode | Sales
| - | Inactive | false

## Example Quotation Section Item XML

```xml
<Item>
    <Id>d3cef410-9819-49a8-b9e3-95bcc01fc065</Id>
    <ProductCode>TEST</ProductCode>
    <Deleted xsi:nil="true" />
    <Information>
        <Description>Test Product</Description>
        <Category>Test Category</Category>
        <CustomFields>
            <CustomField>
                <Label>Custom Field 1</Label>
                <Value>TEST CUSTOM FIELD</Value>
            </CustomField>
            <CustomField>
                <Label>Available To Make up</Label>
            </CustomField>
        </CustomFields>
    </Information>
    <Unit>kgs</Unit>
    <UsePriceBreaks xsi:nil="true" />
    <Quantity>1</Quantity>
    <SetupCost>0</SetupCost>
    <Vat>20</Vat>
    <Markup>0</Markup>
    <Discount>5</Discount>
    <ListPrice>100</ListPrice>
    <Price>95</Price>
    <ListCost>0</ListCost>
    <Cost>0</Cost>
    <LabourName>Test Labour</LabourName>
    <LabourHours>10</LabourHours>
    <LabourRate>1</LabourRate>
    <LabourCostRate>0</LabourCostRate>
    <LabourPrice>10</LabourPrice>
    <LabourCost>0</LabourCost>
    <Margin>100</Margin>
    <MarginPrice>95</MarginPrice>
    <Total>105</Total>
    <ImageUrl>/Product Images/NotFound.png</ImageUrl>
    <IsKit>false</IsKit>
    <IsKitItem>false</IsKitItem>
    <IsComment>false</IsComment>
    <HidePrices>false</HidePrices>
    <CanDelete>true</CanDelete>
    <HideOnPdf>false</HideOnPdf>
    <IsRequired>false</IsRequired>
    <SortPos>0</SortPos>
    <AllowClientToCustomize>false</AllowClientToCustomize>
    <TaxCode>
        <Id>ac3eb80c-a83d-4b64-8516-549a97813b8e</Id>
        <Value>20.0% S</Value>
    </TaxCode>
    <PurchasesAccountCode>
        <Id>8f1afc15-007a-48e2-9e22-1c3b4246826a</Id>
        <Value>Purchases</Value>
    </PurchasesAccountCode>
    <SalesAccountCode>
        <Id>b01b3009-eb1e-41dc-bc14-9568e81313b3</Id>
        <Value>Sales</Value>
    </SalesAccountCode>
    <Inactive>false</Inactive>
</Item>
```
