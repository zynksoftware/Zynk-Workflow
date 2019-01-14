---
slug: quikflw-quotation-xml
title: Quikflw Quotation XML
---

## Unique Identifier

## Quotation Header

| Quikflw Field | XML Field | Example |
| --- | ---| --- |
|  -  | Id | 1ec58ac3-95d8-4373-ade4-7123496e0549 |
|  -  | Client | [See Client XML](Quikflw-Client-XML)
|  -  | Contact | [See Contact XML](Quikflw-Contact-XML)
|  -  | Status/Id | 7
|  -  | Status/Status | Completed
|  -  | Reference |Q
| Client Ref | ClientReference | Quikflw
| Quotation : Q | Number | 1107
| Description | Description | Integration Development
| Note for Client | Note | Client notes
| Discount | DiscountPercentage | 4.55
| Products Margin | MarginPercentage |  90.48
| Products Margin | TotalMargin | 95
| Tax | TotalVat | 21
| Item Costs | TotalCost | 0
| Net | TotalNet | 105
| Total Price | TotalPrice | 126
| Labour Charge Price | TotalLabour | 10
| Labour Cost Price | TotalLabourCost | 0
| - | TotalLabourHours | 10
| - | TotalProfit | 105
| - | Profit | 100
| Price List | PriceList/Value | GBP
| - | Currency/Value | GBP 
| PO Number | PoNumber | 123456789
| Companies -> Account Reference | AccountReference | ZYNK
| Delivery Addr | DeliveryAddress | [See Address XML](Quikflw-Address-XML)
| Invoice Addr | InvoiceAddress | [See Address XML](Quikflw-Address-XML)
| Date Quoted | DateQuoted | 2018-12-21T00:00:00 (ISO 8601)
| No Of Days Valid | NumberDaysValid | 30
| Created by | Created | 2018-12-21T11:32:00.48 (ISO 8601)
| Created by | CreatedBy | projects@zynk.com
| - | LastUpdated | 2018-12-21T13:08:20.383 (ISO 8601)
| Delivery Date | EstimatedDelivery | 2018-12-21T00:00:00 (ISO 8601)
| - | IsApproved | false
| - | IsClientDraft | false
| Client Customization -> Allow Client to Customize Quotation | AllowClientToCustomize | false
| Client Customization -> Allow Client Edit Line Items | AllowClientEditLineItems | false
| Client Customization -> Allow Client Edit Sections | AllowClientEditSections | false
| Client Customization -> Customized Version Needs To Be Checked After Client Submission | NeedsCheckedClientSubmission | false
| - | IsStripePaid | false

## Quotation Sections
| Quikflw Field | XML Field | Example |
| --- | ---| --- |
| - | Id | f3f881f2-dda0-4368-9e8e-292cb3fe0188
| Section Name | Name | Integration Development
| Section Note | Note | Sage 50 &amp; Quikflw
| Include In Total | IncludeInTotal | true
| Hide From Client | HideFromClient | false
| - | IsRequired | false
| - | AllowClientToCustomize | false
| - | CurrencySymbol | £
| Discount | DiscountAmount | 4.55
| Margin | MarginAmount | 90.48
| Labour Charge Price | TotalLabour | 10
| Labour Charge Cost | TotalLabourCost | 0 
| - | TotalLabourHours | 10
| Tax | TotalVat | 21
| - | TotalDiscount | 5
| Margin | TotalMargin | 95
| Cost | TotalCost | 0
| Net | TotalNet | 105
| Total Price | TotalPrice | 126
| Items | Items/Item | [See Item XML](Quikflw-Quotation-Section-Item-XML)

## Example Quotation XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Quotation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Quotation>
    <Id>1ec58ac3-95d8-4373-ade4-7123496e0549</Id>
    <Client>
      <Id>7cbdb9ea-fa4c-4058-804d-3d7c55a6d4b7</Id>
      <Name>Zynk Software Ltd</Name>
      <Address1>i6 Charlotte Square</Address1>
      <Address2>6-8 Charlotte Square</Address2>
      <Town>Newcastle upon Tyne</Town>
      <County>Tyne &amp; Wear</County>
      <Postcode>NE1 4X</Postcode>
      <Country>United Kingdom</Country>
      <Email>andrew.gittus@zynk.com</Email>
      <Telephone>01913037279</Telephone>
      <Website>http://zynk.com</Website>
      <AccountReference>ZYNK</AccountReference>
      <Created>2018-12-21T11:25:45.647</Created>
    </Client>
    <Contact>
      <Id>03ef3dcd-cebc-4549-b978-89ea4e2aa8b4</Id>
      <Client>
        <Id>7cbdb9ea-fa4c-4058-804d-3d7c55a6d4b7</Id>
        <Value>Zynk Software Ltd</Value>
      </Client>
      <Title>Sales</Title>
      <FirstName>Zynk</FirstName>
      <LastName>Sales</LastName>
      <Position>Sales</Position>
      <Telephone>01913037279</Telephone>
      <Email>sales@zynk.com</Email>
      <Address1>i6 Charlotte Square</Address1>
      <Address2>6-8 Charlotte Square</Address2>
      <Town>Newcastle upon Tyne</Town>
      <County>Tyne &amp; Wear</County>
      <Postcode>NE1 4X</Postcode>
      <Country>United Kingdom</Country>
    </Contact>
    <Status>
      <Id>7</Id>
      <Value>Completed</Value>
    </Status>
    <Reference>Q</Reference>
    <ClientReference>Quikflw</ClientReference>
    <Number>1107</Number>
    <Version>1</Version>
    <Description>Integration Development</Description>
    <Note>Client notes</Note>
    <Discount>4.55</Discount>
    <Margin>90.48</Margin>
    <TotalVat>21</TotalVat>
    <TotalMargin>95</TotalMargin>
    <TotalCost>0</TotalCost>
    <TotalNet>105</TotalNet>
    <TotalPrice>126</TotalPrice>
    <TotalLabour>10</TotalLabour>
    <TotalLabourCost>0</TotalLabourCost>
    <TotalLabourHours>10</TotalLabourHours>
    <TotalProfit>105</TotalProfit>
    <Profit>100</Profit>
    <PriceList>
      <Id>de4731b0-bf42-4995-bad5-d4b10e69fe8c</Id>
      <Value>GBP</Value>
    </PriceList>
    <Currency>
      <Id>1</Id>
      <Value>GBP</Value>
    </Currency>
    <PoNumber>123456789</PoNumber>
    <AccountReference>ZYNK</AccountReference>
    <CustomFields />
    <DeliveryAddress>
      <Address1>i6 Charlotte Square</Address1>
      <Address2>6-8 Charlotte Square</Address2>
      <Country>United Kingdom</Country>
      <County>Tyne &amp; Wear</County>
      <Name>Zynk Software Ltd</Name>
      <Postcode>NE1 4X</Postcode>
      <Reference />
      <Town>Newcastle upon Tyne</Town>
    </DeliveryAddress>
    <InvoiceAddress>
      <Address1>i6 Charlotte Square</Address1>
      <Address2>6-8 Charlotte Square</Address2>
      <Country>United Kingdom</Country>
      <County>Tyne &amp; Wear</County>
      <Name>Zynk Software Ltd</Name>
      <Postcode>NE1 4X</Postcode>
      <Reference />
      <Town>Newcastle upon Tyne</Town>
    </InvoiceAddress>
    <DateQuoted>2018-12-21T00:00:00</DateQuoted>
    <NumberDaysValid>30</NumberDaysValid>
    <Created>2018-12-21T11:32:00.48</Created>
    <CreatedBy>projects@zynk.com</CreatedBy>
    <LastUpdated>2019-01-14T09:26:52.68</LastUpdated>
    <EstimatedDelivery>2018-12-21T00:00:00</EstimatedDelivery>
    <IsApproved>false</IsApproved>
    <IsClientDraft>false</IsClientDraft>
    <AllowClientToCustomize>false</AllowClientToCustomize>
    <AllowClientEditLineItems>false</AllowClientEditLineItems>
    <AllowClientEditSections>false</AllowClientEditSections>
    <NeedsCheckedClientSubmission>false</NeedsCheckedClientSubmission>
    <IsStripePaid>false</IsStripePaid>
    <Sections>
      <Section>
        <Id>f3f881f2-dda0-4368-9e8e-292cb3fe0188</Id>
        <Name>Integration Development</Name>
        <Note>Sage 50 &amp;amp; Quikflw</Note>
        <IncludeInTotal>true</IncludeInTotal>
        <HideFromClient>false</HideFromClient>
        <IsRequired>false</IsRequired>
        <AllowClientToCustomize>false</AllowClientToCustomize>
        <SortPos>0</SortPos>
        <CurrencySymbol>£</CurrencySymbol>
        <Discount>4.55</Discount>
        <Margin>90.48</Margin>
        <TotalLabour>10</TotalLabour>
        <TotalLabourCost>0</TotalLabourCost>
        <TotalLabourHours>10</TotalLabourHours>
        <TotalVat>21</TotalVat>
        <TotalDiscount>5</TotalDiscount>
        <TotalMargin>95</TotalMargin>
        <TotalCost>0</TotalCost>
        <TotalNet>105</TotalNet>
        <TotalPrice>126</TotalPrice>
        <Items>
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
        </Items>
      </Section>
    </Sections>
  </Quotation>
</Quotation>
```