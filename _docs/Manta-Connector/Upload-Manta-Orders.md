---
slug: upload-orders-to-manta
title: Upload Orders to Manta
---

This task will create order confirmations within Manta using provided XML. See [below](#examples) for a sample input file.

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
<Orders>
  <Order>
    <ExternalId>70600</ExternalId>
    <BackOrder>true</BackOrder>
    <PoAttached>true</PoAttached>
    <Type>OC</Type>
    <TotalNet>144</TotalNet>
    <TotalVat>0</TotalVat>
    <TotalGross>144</TotalGross>
    <OrderIdBrand>70600</OrderIdBrand>
    <PaymentTerms>30_days_net</PaymentTerms>
    <Document>
      <Content>
        <Name>\path\to\pdf\file\salesorder_report_70600_27862.pdf</Name>
      </Content>
    </Document>
    <OrderItemDetails>
      <OrderItemDetail>
        <PoID>27862</PoID>
        <Items>
          <Item>
            <EstimatedTimeOfDelivery>2018-11-30</EstimatedTimeOfDelivery>
            <Sku>TEST01</Sku>
            <Price>24</Price>
            <Qty>6</Qty>
            <Discount>0</Discount>
            <RowTotalNet>144</RowTotalNet>
            <RowTotalVat>0</RowTotalVat>
            <RowTotalGross>144</RowTotalGross>
          </Item>
        </Items>
      </OrderItemDetail>
    </OrderItemDetails>
  </Order>
</Orders>
```