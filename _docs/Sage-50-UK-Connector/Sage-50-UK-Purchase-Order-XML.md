---
slug: sage-50-uk-purchase-order-xml
title: Sage 50 UK Purchase Order XML
---
Import Purchase Orders allows you to create new orders with Sage 50, and optionally progress the order through the ordering process.  We recommend that the Id field be populated by the unique id of the order from the external system, Zynk uses this field to track orders already imported to prevent duplicates being created in Sage.  

Any fields not documented below are not directly supported with our imports.

Sample import file for creating a basic order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <PurchaseOrderDate>2014-01-01T00:00:00</PurchaseOrderDate>
      <PurchaseOrderAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
      </PurchaseOrderAddress>
      <PurchaseOrderDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
      </PurchaseOrderDeliveryAddress>
      <PurchaseOrderItems>
        <Item>
          <Sku>TEST01</Sku>
          <QtyOrdered>1</QtyOrdered>
          <UnitPrice>200</UnitPrice>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create an order. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Order Details - Account Information
To assign the order to a particular account you will need to specify either a CustomerId or an AccountReference in the XML. The CustomerId should correspond to a supplier that has already been imported into Sage via Zynk, see Import Suppliers. The AccountReference should correspond to the Reference of a Purchase Ledger account that exists with Sage.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| -  | CustomerId  | 123  | string  | 255 | Optional  |
| A/C   | AccountReference  | JOE001  | string  | 8  | Required  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <CustomerId>123</CustomerId>
      <AccountReference>JOE001</AccountReference>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Order Details - Detail

All of the fields at the Order detail level are optional.

Depending on the settings of the import task you can set the Order no of the created order.  If you have enabled Manual Order Numbering at the task level you can specify the PurchaseOrderNumber to use when creating the order, note this must be unique, and if already exists in Sage the order will not be imported.  You can specify the Document date of the order using PurchaseOrderDate.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| -| Id | 123  | string  | 255 | Optional  |
| Order No.  | PurchaseOrderNumber  | 123  | string  | 60  | Optional  |
| Date   | PurchaseOrderDate  | 2014-01-01T00:00:00  | datetime | 8  | Required  |
| Ref  | Reference  | 123  | string  | 7  | Optional  |
| Currency  | Currency*  | EUR   | string  | 3  | Optional |
| Foreign Rate | ForeignRate* | 1.5  | double   | -  | Optional  |
| Name  | Company*  | Zynk Software Limited  | string  | 60  | Optional  |
| Customer Contact*  | FullName*  | Mr Joe E Harrison Jr.  | string  | 30  | Optional  |
| -  | Title   | Mr  | string  | -  | Optional   |
| -  | Forename  | Joe  | string  | -  | Optional   |
| -  | Middlename  | E  | string  | -  | Optional   |
| -  | Surname   | Harrison  | string  | -  | Optional   |
| -  | Suffix   | Jr.  | string  | -  | Optional   |
| Address 1  | Address1  | Nelson House  | string  | 60  | Optional  |
| Address 2  | Address2  | Fleming Business Centre  | string  | 60  | Optional  |
| Address 3  | Address3 + Town  | Jesmond, Newcastle upon Tyne  | string   | 60   | Optional  |
| Address 4  | County  | Tyne and Wear  | string  | 60  | Optional  |
| Address 5  | Postcode  | NE2 3AE  | string   | 60  | Optional  |
| Customer Tel. No.*  | Telephone  | 0845 123 2920  | string  | 60  | Optional  |

*   ForeignRate* - If this is not provided the exchange rate in Sage will be used.

*   Company* - If this field is not set in the XML, it is built up of Title, Forename, Middlename, Surname and Suffix.
*   Customer Contact* / FullName - This field is on the Order Details tab not Details, but included in the PurchaseOrderAddress.  This field is not set directly in the XML, but is built up of Title, Forename, Middlename, Surname and Suffix.    
*   Customer Tel. No.* - This field is on the Order Details tab not Details, but included in thePurchaseOrderAddress.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <Id>123</Id>
      <PurchaseOrderNumber>123</PurchaseOrderNumber>
      <PurchaseOrderDate>2014-01-01T00:00:00</PurchaseOrderDate>
      <Reference>123</Reference>
      <Currency>EUR</Currency>
      <ForeignRate>1.5</ForeignRate>
      <PurchaseOrderAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Suffix>Jr.</Suffix>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House</Address1>
        <Address2>Charlotte</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
        <Telephone>0845 123 2920</Telephone>
      </PurchaseOrderAddress>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Order Detail  
If a delivery address is provided we will use the data in the XML, otherwise we will fall back to use the invoice address of the supplier from Sage. The below fields will only affect the Purchase Order in Sage.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Supplier Order No. | SupplierOrderNumber  | 123  | string | 60  | Optional  |
| Order Taken By  | TakenBy  | Website  | string  | 60  | Optional  |
| Delivery Name | Company* | Zynk Software Limited | string | 60 | Optional |
| -  | Title    | Mr   | string  | -  | Optional  |
| -  | Forename   | Joe  | string  | -  | Optional  |
| -  | Middlename  | E  | string  | -  | Optional  |
| -  | Surname  | Harrison  | string  | -  | Optional  |
| -  | Suffix  | Jr.   | string  | -  | Optional  |
| Delivery Address 1 | Address1 | Nelson House | string | 60 | Optional  |
| Delivery Address 2 | Address2 | Fleming Business Centre | string | 60 | Optional |
| Delivery Address 3 | Address3 + Town | Jesmond, Newcastle upon Tyne | string | 60 | Optional  
| Delivery Address 4 | County | Tyne and Wear  | string | 60 | Optional |
| Delivery Address 5 | Postcode | NE2 3AE | string | 60 | Optional  |
| Notes 1 | Notes1 | Website 1 | string | 60 | Optional  |
| Notes 2 | Notes2 | Leave next door | string | 60 | Optional  |
| Notes 3 | Notes3 | Paid by PayPal  | string  | 60 | Optional   |

 * Company* - If this field is not set in the XML, it is built up of Title, Forename, Middlename, Surname and Suffix.

 ```xml
 <?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <SupplierOrderNumber>123</SupplierOrderNumber>
      <TakenBy>Website</TakenBy>
      <PurchaseOrderDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Suffix>Jr.</Suffix>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House</Address1>
        <Address2>Charlotte</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
        <Telephone>0845 123 2920</Telephone>
      </PurchaseOrderDeliveryAddress>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Footer Details  

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Carriage Net  | UnitPrice | 10 | double | - | Optional |
| Carriage N/C  | NominalCode  |  4905 | string  | 8  | Optional |
|  Carriage Consign. No | ConsignmentNo  | 123  | string  | 30  | Optional |
| Carriage Tax Code | TaxCode  | 1 | int  | 2  | Optional |
| Carriage Department  | Department  | 1 | int  | 2  | Optional |
| Carriage Courier  | Courier | 1  | int | 2  | Optional |
| Settlement Days  | SettlementDays  | 30  | int  | 2  | Optional  |
| Settlement Discount %  | SettlementDiscount  | 2.5  | double  | -  | Optional  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <Carriage>
        <QtyOrdered>1</QtyOrdered>
        <UnitPrice>10</UnitPrice>
        <NominalCode>4905</NominalCode>
        <TaxCode>1</TaxCode>
        <Department>1</Department>
      </Carriage>
      <ConsignmentNo>123</ConsignmentNo>
      <Courier>1</Courier>
      <SettlementDays>30</SettlementDays>
      <SettlementDiscount>2.5</SettlementDiscount>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Details - Items  
We support importing stock items, service items, special lines (S1, S2 and S3) and message lines (M).

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Product Code  | Sku | PROD001 | string  | 30  | Required  |
| Description   | Name  | Sample Product | string  | 60  | Required |
| Comment 1  | Description  | This is a sample product  | string | 60  | Optional  |
| Comment 2 | Comments  | A sample  | string | 60  | Optional  |
| Units | UnitOfSale  | Each  | string   | 8   | Optional   |
| Quantity | QtyOrdered  | 1  | double  | -  | Required  |
| Unit Price  | UnitPrice  | 20 | double  | -  | Optional  | If not specified, Zynk will use the sales price from the product record. |
| Discount % | UnitDiscountPercentage  | 10 | double  | -  | Optional  |
| Discount | UnitDiscountAmount | 2  | double  | -  | Optional  |
| Nominal Code  | NominalCode  | 4000 | string  | 8  | Optional  | If not specified, Zynk will use the default nominal code associated with the supplier. If no default nominal code is found for the supplier, Zynk will use the default nominal code associated with the product record.  |
| TaxCode  | TaxCode
 | 1  | int  | 2  | Optional  | If not specified, Zynk will use the default tax code associated with the product, or the default tax code associated with the supplier if the 'Use Default Tax Code for Sales' option is enabled on the customer record. |
| Department  | Department  | 1 | int  | 2  | Optional  |
| Line Information  | Reference  | Sample Job | string  | 60  | Optional  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
     <PurchaseOrderItems>
       <Item>
          <Sku>PROD001</Sku>
          <Name>Sample Product</Name>
          <Description>This is a sample product</Description>
          <Comments>A sample</Comments>
          <UnitOfSale>Each</UnitOfSale>
          <QtyOrdered>1</QtyOrdered>
          <UnitPrice>20.00</UnitPrice>
          <UnitDiscountPercentage>10</UnitDiscountPercentage>
          <UnitDiscountAmount>2.00</UnitDiscountAmount>
          <NominalCode>4000</NominalCode>
          <TaxCode>1</TaxCode>
          <Department>1</Department>
          <Reference>Sample Job</Reference>
       </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```
