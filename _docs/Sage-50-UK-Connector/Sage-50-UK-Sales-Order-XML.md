---
slug: sage-50-uk-sales-order-xml
title: Sage 50 UK Sales Order XML
---
Import Sales Orders allows you to create new orders with Sage 50, and optionally progress the order through the ordering process.  We recommend that the Id field be populated by the unique id of the order from the external system, Zynk uses this field to track orders already imported to prevent duplicates being created in Sage.  

Any fields not documented below are not directly supported with our imports.

Sample import file for creating a basic order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <SalesOrderDate>2014-01-01T00:00:00</SalesOrderDate>
      <VatInclusive>true</VatInclusive>
      <SalesOrderAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
      </SalesOrderAddress>
      <SalesOrderDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
      </SalesOrderDeliveryAddress>
      <SalesOrderItems>
        <Item>
          <Sku>TEST01</Sku>
          <QtyOrdered>1</QtyOrdered>
          <UnitPrice>200</UnitPrice>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create an order. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Account Information  
To assign the order to a particular account you will need to specify either a CustomerId or an AccountReference in the XML. The CustomerId should correspond to a customer that has already been imported into Sage via Zynk, see Import Customer. The AccountReference should correspond to the Reference of a Sales Ledger account that exists with Sage.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| -  | CustomerId  | 123  | string  | 255 | Optional  |
| A/C   | AccountReference  | JOE001  | string  | 8  | Required  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <CustomerId>123</CustomerId>
      <AccountReference>JOE001</AccountReference>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Details  
Depending on the settings of the import task you can set the Order no of the created order.  If you have enabled Manual Order Numbering at the task level you can specify the SalesOrderNumber to use when creating the order, note this must be unique, and if already exists in Sage the order will not be imported.  You can specify the Document date of the order using SalesOrderDate.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| - | Id | 123  | string  | 255 | Optional  |
| Order No.  | SalesOrderNumber* | 123  | string  | 7 | Optional  |
| Date   | SalesOrderDate* | 2014-01-01T00:00:00  | datetime | 8  | Optional  |
| Type  | SalesOrderType*  | ProductInvoice  | enum  | -  | Optional  |
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
| Address 4  | County  | Tyne & Wear  | string  | 60  | Optional  |
| Address 5  | Postcode  | NE2 3AE  | string   | 60  | Optional  |
| Customer Tel. No.*  | Telephone  | 0845 123 2920  | string  | 60  | Optional  |
| Net Value Description  | NetValueDiscountDescription  | Website Discount | string  | 60  | Optional  |
| Net Value Comment 1  | NetValueDiscountComment1 | January Offer | string  | 60  | Optional  |
| Net Value Comment 2  | NetValueDiscountComment2  | 10% Off | string  | 60  | Optional  |
| Net Value Discount %  | NetValueDiscountPercent  | 10  | double  | -  | Optional  |
| Net Value Disc.  | NetValueDiscount | 10  | double  | -  | Optional  |

*   SalesOrderNumber* - Only used if the Use Manual Sales Order Number setting is enabled on the task, otherwise the next available sales order number will be used instead.

*   SalesOrderDate* - If this is not provided, it will default to today's date.

*   SalesOrderType* - This field can be either ProductInvoice, SopInvoice, SopQuote, SopProforma.  Defaults to ProductInvoice.
*   Currency* - If this is not provided the account currency will be used.  If it is provided but does not match the account currency the import will fail unless Convert to Account Currency is enabled on the task.

*   ForeignRate* - If this is not provided the exchange rate in Sage will be used.

*   Company* - If this field is not set in the XML, it is built up of Title, Forename, Middlename, Surname and Suffix.
*   Customer Contact* / FullName - This field is on the Order Details tab not Details, but included in the SalesOrderAddress.  This field is not set directly in the XML, but is built up of Title, Forename, Middlename, Surname and Suffix.    
*   Customer Tel. No.* - This field is on the Order Details tab not Details, but included in the SalesOrderAddress.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <Id>123</Id>
      <SalesOrderNumber>123</SalesOrderNumber>
      <SalesOrderDate>2014-01-01T00:00:00</SalesOrderDate>
      <SalesOrderType>ProductInvoice</SalesOrderType>
      <Currency>EUR</Currency>
      <ForeignRate>1.5</ForeignRate>
      <VatInclusive>true</VatInclusive>
      <SalesOrderAddress>
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
        <County>Tyne &amp; Wear</County>
        <Telephone>0845 123 2920</Telephone>
      </SalesOrderAddress>
      <NetValueDiscountDescription>Website Discount</NetValueDiscountDescription>
      <NetValueDiscountComment1>January Offer</NetValueDiscountComment1>
      <NetValueDiscountComment2>10% Off</NetValueDiscountComment2>
      <NetValueDiscountPercent>10</NetValueDiscountPercent>
      <NetValueDiscount>1.80</NetValueDiscount>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Order Details  
If a delivery address is provided we will use the data in the XML, otherwise we will fall back to use the invoice address of the customer from Sage. The below fields will only affect the Sales Order in Sage.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Customer Order No. | CustomerOrderNumber  | 123  | string | 60  | Optional  |
| Order Taken By  | TakenBy  | Website  | string  | 60  | Optional  |
| Delivery Name | Company* | Zynk Software Limited | string | 60 | Optional |
| -  | Title    | Mr   | string  | -  | Optional  |
| -  | Forename   | Joe  | string  | -  | Optional  |
| -  | Middlename  | E  | string  | -  | Optional  |
| -  | Surname  | Harrison  | string  | -  | Optional  |
| -  | Suffix  | Jr.   | string  | -  | Optional  |
| Delivery Address 1 | Address1 | Nelson House | string | 60 | Optional  |
| Delivery Address 2 | Address2 | Fleming Business Centre | string | 60 | Optional |
| Delivery Address 3 | Address3 + Town | Jesmond, Newcastle upon Tyne | string | 60 | Optional  |
| Delivery Address 4 | County | Tyne & Wear  | string | 60 | Optional |
| Delivery Address 5 | Postcode | NE2 3AE  | string | 60 | Optional  |
| Notes 1 | Notes1 | Website 1 | string | 60 | Optional  |
| Notes 2 | Notes2 | Leave next door | string | 60 | Optional  |
| Notes 3 | Notes3 | Paid by PayPal  | string  | 60 | Optional   |
| VatInclusive | VatInclusive | true | boolean | - | Optional |
| Due  | DespatchDate | 2014-01-01T00:00:00 | datetime | - | Optional |
| Custom Field 1* | Custom1 | Royal Mail Tracked | string | 60 | Optional |
| Custom Field 2* | Custom2 | Next Day | string | 60 | Optional |
| Custom Field 3* | Custom2 | DR35087BK923 | string | 60 | Optional |

*   Company* - If this field is not set in the XML, it is built up of Title, Forename, Middlename, Surname and Suffix.
*   Custom Field* - These fields can be renamed via the settings in Sage, so may appear differenly. The defaults are Analysis1, Analysis2 and Analysis3.
*  Vat Inclusive* - If not provided will default to the relevant VAT settings in Sage

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <CustomerOrderNumber>123</CustomerOrderNumber>
      <TakenBy>Website</TakenBy>
      <SalesOrderDeliveryAddress>
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
        <County>Tyne &amp; Wear</County>
      </SalesOrderDeliveryAddress>
      <Notes1>Website 1</Notes1>
      <Notes2>Leave next door</Notes2>
      <Notes3>Paid by PayPal</Notes3>
      <DespatchDate>2014-01-01T00:00:00</DespatchDate>
      <Custom1>Royal Mail Tracked</Custom1>
      <Custom2>Next Day</Custom2>
      <Custom3>DR35087BK923</Custom3>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Footer Details

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Carriage Net  | UnitPrice | 10 | double | - | Optional |
| Carriage N/C  | NominalCode  |  4905 | string  | 8  | Optional |
| Carriage Consign. No | ConsignmentNo  | 123  | string  | 30  | Optional |
| Carriage Tax Code | TaxCode  | 1 | int  | 2  | Optional |
| Carriage Department  | Department  | 1 | int  | 2  | Optional |
| Carriage Courier  | Courier | 1  | int | 2  | Optional |
| Settlement Days  | SettlementDays  | 30  | int  | 2  | Optional  |
| Settlement Discount %  | SettlementDiscount  | 2.5  | double  | -  | Optional  |
| Global N/C  | GlobalNominalCode  | 4000  | string  | 8  | Optional  |
| Global Tax Code  | GlobalTaxCode  | 1  | int  | 2  | Optional  |
| Global Details  | GlobalDetails  | Sales  | string  | 60  | Optional  |
| Global Department  | GlobalDepartment  | 1  | int  | 2  | Optional  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <Carriage>
        <UnitPrice>10</UnitPrice>
        <NominalCode>4905</NominalCode>
        <TaxCode>1</TaxCode>
        <Department>1</Department>
      </Carriage>
      <ConsignmentNo>123</ConsignmentNo>
      <Courier>1</Courier>
      <SettlementDays>30</SettlementDays>
      <SettlementDiscount>2.5</SettlementDiscount>
      <GlobalNominalCode>4000</GlobalNominalCode>
      <GlobalTaxCode>1</GlobalTaxCode>
      <GlobalDetails>Sales</GlobalDetails>
      <GlobalDepartment>1</GlobalDepartment>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Payment Details  

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Payment Ref | PaymentRef | PayPal  | string  | 30  | Optional  |
| Bank Account | BankAccount | 1200 | string  | 8  | Required and must equate to a valid Bank in Sage to populate Payment Details |
| Payment Amount | PaymentAmount  | 100  | double  | -  | Required and greater than 0 to populate Payment Details |
| PaymentType  | PaymentType*  | SalesReceipt  | enum  | -  | Required to populate Payment Details |

*   PaymentType* - This field can either be:-

*   SalesReceipt - will copy the payment information to the generate invoice.  Once the invoice is posted the payment will be created on the account and allocated
*   PaymentAlreadyReceived - will check the Payment already received radio button on the Payment tab.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <PaymentRef>PayPal</PaymentRef>
      <BankAccount>1200</BankAccount>
      <PaymentAmount>31.36</PaymentAmount>
      <PaymentType>SalesReceipt</PaymentType>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Details - Items  
We support importing stock items, service items, special lines (S1, S2 and S3) and message lines (M).

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |  Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Product Code  | Sku | PROD001 | string  | 30  | Required  |
| Description   | Name  | Sample Product | string  | 60  | Optional | If not specified, Zynk will use the description from the product record.|
| Comment 1  | Description  | This is a sample product  | string | 60  | Optional  |
| Comment 2 | Comments  | A sample  | string | 60  | Optional  |
| Units | UnitOfSale  | Each  | string   | 8   | Optional   |
| Quantity | QtyOrdered  | 1  | double  | -  | Required  |
| Unit Price  | UnitPrice  | 20 | double  | -  | Optional | If not specified, Zynk will use the sales price from the product record.|
| Discount % | UnitDiscountPercentage  | 10 | double  | -  | Optional  |
| Discount | UnitDiscountAmount | 2  | double  | -  | Optional  |
| Nominal Code  | NominalCode  | 4000 | string  | 8  | Optional  | If not specified, Zynk will use the default nominal code associated with the product, or the default nominal code associated with the customer if the 'Use Default Nominal Code for Sales' option is enabled on the customer record. |
| Tax Code  | TaxCode| 1  | int  | 2  | Optional  | If not specified, Zynk will use the default tax code associated with the product, or the default tax code associated with the customer if the 'Use Default Tax Code for Sales' option is enabled on the customer record.|
| Department  | Department  | 1 | int  | 2  | Optional  |
| Line Information  | Reference  | Sample Job | string  | 60  | Optional  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
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
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```
