---
slug: sage-50-uk-invoice-xml
title: Sage 50 UK Invoice XML
---
Import Invoices allows you to create new invoices within Sage 50.  We recommend that the Id field be populated by the unique id of the invoice from the external system, Zynk uses this field to track invoices already imported to prevent duplicates being created in Sage.  

Any fields not documented below are not directly supported with our imports.

Sample import file for creating a basic invoice:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Invoices>
    <Invoice>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <InvoiceType>ProductInvoice</InvoiceType>
      <InvoiceNumber>123</InvoiceNumber>
      <InvoiceDate>2014-01-01T00:00:00</InvoiceDate>
      <CustomerOrderNumber>123</CustomerOrderNumber>
      <Currency>EUR</Currency>
      <ForeignRate>1.5</ForeignRate>
      <InvoiceAddress>
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
      </InvoiceAddress>
      <NetValueDiscountDescription>Website Discount</NetValueDiscountDescription>
      <NetValueDiscountComment1>January Offer</NetValueDiscountComment1>
      <NetValueDiscountComment2>10% Off</NetValueDiscountComment2>
      <NetValueDiscountPercent>10</NetValueDiscountPercent>
      <NetValueDiscount>1.80</NetValueDiscount>
    </Invoice>
  </Invoices>
</Company>
```

## Supported Invoice Types
The InvoiceType field can be one of the following:
 * ProductInvoice
 * ProductCredit
 * ServiceInvoice
 * ProductProforma
 * ServiceProforma
 * ProductQuotation

## Account Information
To assign the order to a particular account you will need to specify either a CustomerId or an AccountReference in the XML. The CustomerId should correspond to a customer that has already been imported into Sage via Zynk, see Import Customers task. The AccountReference should correspond to the Reference of a Sales Ledger account that exists with Sage.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| - | CustomerId | 123 | string | 255 | Optional |
| A/C  | AccountReference | JOE001 | string | 8 | Required |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Invoices>
    <Invoice>
      <CustomerId>123</CustomerId>
      <AccountReference>JOE001</AccountReference>
    </Invoice>
  </Invoices>
</Company>
```

## Details
The following fields can be set on the details tab.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Type | InvoiceType | ProductInvoice | enum | - | Optional |
| Date  | InvoiceDate\* | 2014-01-01T00:00:00 | datetime | - | Optional |
| Inv. No. | InvoiceNumber | 123 | string | 7 | Optional |
| Order No | OrderNumber | 456 | string | 7 | Optional |
| Due On | DueDate | 2014-01-31 | datetime | - | Optional |
| Invoice Name | InvoiceAddress/Company\* | Zynk Software Limited | string | 60 | Optional |
| - | Title  | Mr | string | - | Optional |
| - | Forename | Joe | string | - | Optional |
| - | Middlename | E | string | - | Optional |
| - | Surname | Harrison | string | - | Optional |
| - | Suffix | Jr. | string | - | Optional |
| Invoice Addresss 1 | InvoiceAddress/Address1 | Nelson House | string | 60 | Optional |
| Invoice Address 2 | InvoiceAddress/Address2 | Fleming Business Centre | string | 60 | Optional |
| Invoice Address 3 | InvoiceAddress/Address3 + Town | Jesmond, Newcastle upon Tyne | string | 60 | Optional |
| Invoice Address 4 | InvoiceAddress/County | Tyne and Wear | string | 60 | Optional |
| Invoice Address 5 | InvoiceAddress/Postcode | NE2 3AE | string | 60 | Optional |
| Net Value Description | NetValueDiscountDescription | Website Discount | string | 60 | Optional |
| Net Value Comment 1 | NetValueDiscountComment1 | January Offer | string | 60 | Optional |
| Net Value Comment 2 | NetValueDiscountComment2 | 10% Off | string | 60 | Optional |
| Net Value Discount % | NetValueDiscountPercent | 10 | double | - | Optional |
| Net Value Disc. | NetValueDiscount | 10 | double | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Invoices>
    <Invoice>
      <InvoiceType>ProductInvoice</InvoiceType>
      <InvoiceDate>2014-01-01T00:00:00</InvoiceDate>
      <InvoiceNumber>123</InvoiceNumber>
      <OrderNumber>456</OrderNumber>
      <DueDate>2014-01-31</DueDate>
      <InvoiceAddress>
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
      </InvoiceAddress>      
      <NetValueDiscountDescription>Website Discount</NetValueDiscountDescription>
      <NetValueDiscountComment1>January Offer</NetValueDiscountComment1>
      <NetValueDiscountComment2>10% Off</NetValueDiscountComment2>
      <NetValueDiscountPercent>10</NetValueDiscountPercent>
      <NetValueDiscount>1.80</NetValueDiscount>
    </Invoice>
  </Invoices>
</Company>
```

## Order Details
If a delivery address is provided we will use the data in the XML, otherwise we will fall back to use the invoice address of the customer from Sage. The below fields will only affect the Sales Order in Sage.  

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Customer Order No. | CustomerOrderNumber | 123 | string | 60 | Optional |
| Order Taken By | TakenBy | Website | string | 60 | Optional |
| Delivery Name | Company\* | Zynk Software Limited | string | 60 | Optional |
| - | Title  | Mr | string | - | Optional |
| - | Forename | Joe | string | - | Optional |
| - | Middlename | E | string | - | Optional |
| - | Surname | Harrison | string | - | Optional |
| - | Suffix | Jr. | string | - | Optional |
| Delivery Address 1 | Address1 | Nelson House | string | 60 | Optional |
| Delivery Address 2 | Address2 | Fleming Business Centre | string | 60 | Optional |
| Delivery Address 3 | Address3 + Town | Jesmond, Newcastle upon Tyne | string | 60 | Optional |
| Delivery Address 4 | County | Tyne and Wear | string | 60 | Optional |
| Delivery Address 5 | Postcode | NE2 3AE | string | 60 | Optional |
| Notes 1  | Notes1 | Website 1  | string | 60  | Optional |
| Notes 2 | Notes2  | Leave next door  | string | 60  | Optional |
| Notes 3 | Notes3 | Paid by PayPal | string | 60 | Optional |

 * Company* - If this field is not set in the XML, it is built up of Title, Forename, Middlename, Surname and Suffix.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Invoices>
    <Invoice>
      <CustomerOrderNumber>123</CustomerOrderNumber>
      <TakenBy>Website</TakenBy>
      <InvoiceDeliveryAddress>
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
      </InvoiceDeliveryAddress>
      <Notes1>Website 1</Notes1>
      <Notes2>Leave next door</Notes2>
      <Notes3>Paid by PayPal</Notes3>
    </Invoice>
  </Invoices>
</Company>
```

## Footer Details  

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Carriage Net | UnitPrice | 10 | double | - | Optional |
| Carriage N/C | NominalCode | 4905 | string | 8 | Optional |
| Carriage Consign. No | ConsignmentNo | 123 | string | 30 | Optional |
| Carriage Tax Code | TaxCode | 1 | int | 2 | Optional |
| Carriage Department | Department | 1 | int | 2 | Optional |
| Carriage Courier | Courier | 1 | int | 2 | Optional |
| Settlement Days | SettlementDays | 30 | int | 2 | Optional |
| Settlement Discount % | SettlementDiscount | 2.5 | double | - | Optional |
| Global N/C | GlobalNominalCode | 4000 | string | 8 | Optional |
| Global Tax Code | GlobalTaxCode | 1 | int | 2 | Optional |
| Global Details | GlobalDetails | Sales | string | 60 | Optional |
| Global Department | GlobalDepartment | 1 | int | 2 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Invoices>
   <Invoice>
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
      <GlobalNominalCode>4000</GlobalNominalCode>
      <GlobalTaxCode>1</GlobalTaxCode>
      <GlobalDetails>Sales</GlobalDetails>
      <GlobalDepartment>1</GlobalDepartment>
   </Invoice>
  </Invoices>
</Company>
```

## Payment Details  

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Payment Ref | PaymentRef | PayPal | string | 30 | Optional |
| Bank Account | BankAccount | 1200 | string | 8 | Optional |
| Payment Amount | PaymentAmount | 100 | double | - | Optional |
| PaymentType | PaymentType\* | SalesReceipt | enum | - | Optional |

 * PaymentType* - This field can either be:-
   * SalesReceipt - When the invoice is posted the payment will be created on the account and allocated
   * SalesReceiptOnAccount - will create the payment on the account when the invoice is posted but will not allocate

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Invoices>
    <Invoice>
      <PaymentRef>PayPal</PaymentRef>
      <BankAccount>1200</BankAccount>
      <PaymentAmount>31.36</PaymentAmount>
      <PaymentType>SalesReceipt</PaymentType>
    </Invoice>
  </Invoices>
</Company>
```

## Details - Items  
We support importing stock items, service items, special lines (S1, S2 and S3) and message lines (M).



| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Product Code | Sku | PROD001 | string | 30 | Required\* |  |
| Description  | Name | Sample Product | string | 60 | Optional   | If not specified, Zynk will use the description from the product record.  |
| Details | Details | This is a Service Invoice product  | string | 60 | Optional   | For Service Invoices Only. Used to capture service line information.  |
| Comment 1 | Description | This is a sample product | string | 60 | Optional |  |
| Comment 2 | Comments | A sample | string | 60 | Optional |  |
| Units | UnitOfSale | Each | string | 8 | Optional |  |
| Quantity | QtyOrdered | 1 | double | - | Required |  |
| Unit Price | UnitPrice | 20 | double | - | Optional  | If not specified, Zynk will use the sales price from the product record. |
| Discount % | UnitDiscountPercentage | 10 | double | - | Optional |  |
| Discount | UnitDiscountAmount | 2 | double | - | Optional |  |
| Nominal Code | NominalCode | 4000 | string | 8 | Optional | If not specified, Zynk will use the default nominal code associated with the product, or the default nominal                code associated with the customer if the 'Use Default Nominal Code for Sales' option is enabled on the customer                record.  |
| Tax Code | TaxCode   | 1 | int | 2 | Optional | If not specified, Zynk will use the default tax code associated with the product, or the default tax code associated                with the customer if the 'Use Default Tax Code for Sales' option is enabled on the customer record.  |
| Department | Department | 1 | int | 2 | Optional |  |
| Make negative | IsNegativeLine | false | boolean | - | Optional | The unit price should always be specified as a positive number. Set this to true to import the unit price as a negative amount. |
| Line Information | Reference | Sample Job | string | 60 | Optional |  |

 * Sku* - Required when importing the following InvoiceType:-
   * ProductInvoice
   * ProductCredit
   * ProductProforma 
   * ProductQuotation 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Invoices>
    <Invoice>
     <InvoiceItems>
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
          <IsNegativeLine>false</IsNegativeLine>
          <Reference>Sample Job</Reference>
        </Item>
      </InvoiceItems>
    </Invoice>
  </Invoices>
</Company>
```
