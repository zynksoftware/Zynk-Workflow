---
slug: exporting-quotations-from-quikflw
title: Exporting Quotations from Quikflw
---

This task will export quotations from Quikflw in [Quikflw Quotation XML]() format to a file.

## Settings
### Quikflw Connection
_Required_  
The connection to Quikflw to use. See the [Connecting to Quikflw] article if you require further information on how to create/manage the connection to Quikflw.

### Export Settings > Date Modified
_Required_  
Only quotations updated after this date will be downloaded. This date is automatically updated each time the task runs with the highest updated date.

### Export Settings > Export Status
_Required_  
_Default Value :_ Draft   
Status of the quotations to export from Quikflw.   
The following status are supported:
* Draft
* Sent
* Accepted
* Declined
* Commenced
* Completed

### Export Settings > Page Size
_Required_  
_Default Value :_ 50   
The number of records to include in each page of records. Increasing this value will increase the speed of the download, however, more of memory (RAM) will be consumed.

### Output File
_Required_   
The name of the file to export the quotations to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file, for full documentation and samples see [Quikflw Quotation XML](quikflw-quotation-xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<Quotations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Quotation>
    <Id>9138b32c-eb27-4199-aa05-061c30e86a31</Id>
    <Client>
      <Id>7cf70a56-eadc-45f0-8222-3749411ceab1</Id>
      <Value>Sample Client 1</Value>
    </Client>
    <Contact>
      <Id>e290edb6-2b51-4c67-8b5f-a13462e3afc6</Id>
      <Value>Mr Donald Draper</Value>
    </Contact>
    <Status>
      <Id>1</Id>
      <Value>Draft</Value>
    </Status>
    <Reference>Q</Reference>
    <ClientReference />
    <Number>1000</Number>
    <Version>1</Version>
    <Description>Sample Quotation 1</Description>
    <Note />
    <Discount>0</Discount>
    <Margin>3.47</Margin>
    <TotalVat>44</TotalVat>
    <TotalMargin>10</TotalMargin>
    <TotalCost>110</TotalCost>
    <TotalNet>320</TotalNet>
    <TotalPrice>364</TotalPrice>
    <TotalLabour>200</TotalLabour>
    <TotalLabourCost>20</TotalLabourCost>
    <TotalLabourHours>2</TotalLabourHours>
    <TotalProfit>190</TotalProfit>
    <Profit>59.375</Profit>
    <PriceList>
      <Id>de4731b0-bf42-4995-bad5-d4b10e69fe8c</Id>
      <Value>GBP</Value>
    </PriceList>
    <Currency>
      <Id>1</Id>
      <Value>GBP</Value>
    </Currency>
    <CustomFields />
    <InvoiceAddress>Sample Client 1, 40 Brunswick Square, Bloomsbury, London, WC1N 1AZ</InvoiceAddress>
    <DeliveryAddress>Sample Client 1, 40 Brunswick Square, Bloomsbury, London, WC1N 1AZ</DeliveryAddress>
    <DateQuoted>2018-11-01T00:00:00</DateQuoted>
    <NumberDaysValid>0</NumberDaysValid>
    <Created>2018-11-01T10:29:49.757</Created>
    <LastUpdated>2018-11-05T11:46:21.723</LastUpdated>
    <EstimatedDelivery>2018-11-01T00:00:00</EstimatedDelivery>
    <IsApproved>false</IsApproved>
    <IsClientDraft>false</IsClientDraft>
    <AllowClientToCustomize>false</AllowClientToCustomize>
    <AllowClientEditLineItems>false</AllowClientEditLineItems>
    <AllowClientEditSections>false</AllowClientEditSections>
    <NeedsCheckedClientSubmission>false</NeedsCheckedClientSubmission>
    <IsStripePaid>false</IsStripePaid>
    <Sections>
      <Section>
        <Id>c79e6dca-6883-4789-bdca-9dc7987bd0fb</Id>
        <IncludeInTotal>true</IncludeInTotal>
        <HideFromClient>false</HideFromClient>
        <IsRequired>false</IsRequired>
        <AllowClientToCustomize>false</AllowClientToCustomize>
        <SortPos>0</SortPos>
        <CurrencySymbol>£</CurrencySymbol>
        <Discount>0</Discount>
        <Margin>2.38</Margin>
        <TotalLabour>100</TotalLabour>
        <TotalLabourCost>10</TotalLabourCost>
        <TotalLabourHours>1</TotalLabourHours>
        <TotalVat>22</TotalVat>
        <TotalDiscount>0</TotalDiscount>
        <TotalMargin>5</TotalMargin>
        <TotalCost>105</TotalCost>
        <TotalNet>210</TotalNet>
        <TotalPrice>232</TotalPrice>
        <Items>
          <Product>
            <Id>80d0f5ad-000e-4a15-a246-300163eae039</Id>
            <ProductCode>QL-1</ProductCode>
            <Deleted xsi:nil="true" />
            <Information>
              <Description>Quotation Line Item 1</Description>
              <Category />
              <CustomFields />
            </Information>
            <UsePriceBreaks xsi:nil="true" />
            <Quantity>5</Quantity>
            <SetupCost>0</SetupCost>
            <Vat>0</Vat>
            <Markup>0</Markup>
            <Discount>0</Discount>
            <ListPrice>0</ListPrice>
            <Price>10</Price>
            <ListCost>0</ListCost>
            <Cost>10</Cost>
            <LabourName />
            <LabourHours>0</LabourHours>
            <LabourRate>0</LabourRate>
            <LabourCostRate>0</LabourCostRate>
            <LabourPrice>0</LabourPrice>
            <LabourCost>0</LabourCost>
            <Margin>0</Margin>
            <MarginPrice>0</MarginPrice>
            <Total>50</Total>
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
          </Product>
          <Product>
            <Id>78b449ca-68ee-46ec-8ab8-25a182d48987</Id>
            <ProductCode>QL-2</ProductCode>
            <Deleted xsi:nil="true" />
            <Information>
              <Description>Quotation Line Item 2</Description>
              <Category />
              <CustomFields />
            </Information>
            <UsePriceBreaks xsi:nil="true" />
            <Quantity>4</Quantity>
            <SetupCost>0</SetupCost>
            <Vat>0</Vat>
            <Markup>0</Markup>
            <Discount>0</Discount>
            <ListPrice>0</ListPrice>
            <Price>5</Price>
            <ListCost>0</ListCost>
            <Cost>5</Cost>
            <LabourName />
            <LabourHours>0</LabourHours>
            <LabourRate>0</LabourRate>
            <LabourCostRate>0</LabourCostRate>
            <LabourPrice>0</LabourPrice>
            <LabourCost>0</LabourCost>
            <Margin>0</Margin>
            <MarginPrice>0</MarginPrice>
            <Total>20</Total>
            <ImageUrl>/Product Images/NotFound.png</ImageUrl>
            <IsKit>false</IsKit>
            <IsKitItem>false</IsKitItem>
            <IsComment>false</IsComment>
            <HidePrices>false</HidePrices>
            <CanDelete>true</CanDelete>
            <HideOnPdf>false</HideOnPdf>
            <IsRequired>false</IsRequired>
            <SortPos>1</SortPos>
            <AllowClientToCustomize>false</AllowClientToCustomize>
          </Product>
          <Product>
            <Id>390bf781-12a8-4d5b-9e74-2a0c2442a18f</Id>
            <ProductCode>QL-3</ProductCode>
            <Deleted xsi:nil="true" />
            <Information>
              <Description>Quotation Line Item 3</Description>
              <Category />
              <CustomFields />
            </Information>
            <UsePriceBreaks xsi:nil="true" />
            <Quantity>1</Quantity>
            <SetupCost>0</SetupCost>
            <Vat>0</Vat>
            <Markup>0</Markup>
            <Discount>0</Discount>
            <ListPrice>0</ListPrice>
            <Price>30</Price>
            <ListCost>0</ListCost>
            <Cost>30</Cost>
            <LabourName />
            <LabourHours>0</LabourHours>
            <LabourRate>0</LabourRate>
            <LabourCostRate>0</LabourCostRate>
            <LabourPrice>0</LabourPrice>
            <LabourCost>0</LabourCost>
            <Margin>0</Margin>
            <MarginPrice>0</MarginPrice>
            <Total>30</Total>
            <ImageUrl>/Product Images/NotFound.png</ImageUrl>
            <IsKit>false</IsKit>
            <IsKitItem>false</IsKitItem>
            <IsComment>false</IsComment>
            <HidePrices>false</HidePrices>
            <CanDelete>true</CanDelete>
            <HideOnPdf>false</HideOnPdf>
            <IsRequired>false</IsRequired>
            <SortPos>2</SortPos>
            <AllowClientToCustomize>false</AllowClientToCustomize>
          </Product>
          <Product>
            <Id>8ab51d46-c502-47fa-b8d0-fedfb0a2d6a8</Id>
            <ProductCode>PARMA-VIOLETS</ProductCode>
            <Deleted xsi:nil="true" />
            <Information>
              <Description>The sweets are hard, biconcave disc-shaped sweets.</Description>
              <Category>Test</Category>
              <CustomFields />
            </Information>
            <Unit>KGs</Unit>
            <UsePriceBreaks xsi:nil="true" />
            <Quantity>1</Quantity>
            <SetupCost>0</SetupCost>
            <Vat>20</Vat>
            <Markup>100</Markup>
            <Discount>0</Discount>
            <ListPrice>10</ListPrice>
            <Price>10</Price>
            <ListCost>5</ListCost>
            <Cost>5</Cost>
            <LabourName>Andrew</LabourName>
            <LabourHours>1</LabourHours>
            <LabourRate>100</LabourRate>
            <LabourCostRate>10</LabourCostRate>
            <LabourPrice>100</LabourPrice>
            <LabourCost>10</LabourCost>
            <Margin>50</Margin>
            <MarginPrice>5</MarginPrice>
            <Total>110</Total>
            <ImageUrl>/Uploads/d47d3087-9de2-464c-bad4-0982ef0668af/Images/b066fdca-6022-432b-8805-e8547f1dc813.jpeg</ImageUrl>
            <IsKit>true</IsKit>
            <IsKitItem>false</IsKitItem>
            <IsComment>false</IsComment>
            <HidePrices>false</HidePrices>
            <CanDelete>true</CanDelete>
            <HideOnPdf>false</HideOnPdf>
            <IsRequired>false</IsRequired>
            <SortPos>3</SortPos>
            <AllowClientToCustomize>false</AllowClientToCustomize>
          </Product>
        </Items>
      </Section>
    </Sections>
  </Quotation>
</Quotations>
```