---
slug: upload-invoices-to-manta
title: Upload Invoices to Manta
---

This task will create invoices within Manta using provided XML. See [below](#examples) for a sample input file.

## Settings
### Connection Settings
#### Manta Connection
_Required_  
The connection to Manta to use. See the [Connecting to Manta](connecting-to-manta) article if you require further information on how to create/manage the connection to Manta.

### File Settings
#### Fail File
_Required_  
The file containing the orders that failed to be uploaded to Manta.

#### Input File
_Required_  
The file containing the orders to update in Manta.

#### Success File
_Required_  
The file containing the orders that were successfully uploaded to Manta.

### Import Settings
#### Prevent Reprocessing
_Required_   
Set to 'True' to prevent the same record being processed more than once. In order for this setting to work, an `<ExternalId>` element must be provided within the XML document.

### Zynk Settings
See [Common Task Settings](common-task-settings).

### Examples
Sample input file for uploading orders to Manta.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Invoices>
  <Invoice>
    <ExternalId>71515</ExternalId>
    <BrandInvoiceId>71515</BrandInvoiceId>
    <InvoiceDate>2018-10-18</InvoiceDate>
    <DueDate>2018-10-28</DueDate>
    <TotalNet>26.4</TotalNet>
    <TotalVat>0</TotalVat>
    <TotalGross>26.4</TotalGross>
    <OrderInvoiceStatus>complete</OrderInvoiceStatus>
    <Order>
      <CompanyBrandCode>ZYNK001</CompanyBrandCode>
      <OrderIdBrand>70680</OrderIdBrand>
    </Order>
    <Document>
      <Content>
        <Name>\path\to\pdf\file\invoice_report_71515_70680.pdf</Name>
      </Content>
    </Document>
    <Items>
      <Item>
        <Sku>TEST01</Sku>
        <Price>4.4</Price>
        <Qty>6</Qty>
        <Discount>0</Discount>
        <RowTotalNet>26.4</RowTotalNet>
        <RowTotalVat>0</RowTotalVat>
        <RowTotalGross>26.4</RowTotalGross>
      </Item>
    </Items>
  </Invoice>
</Invoices>
```