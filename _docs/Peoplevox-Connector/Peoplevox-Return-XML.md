---
slug: peoplevox-return-xml
title: Peoplevox Return XML
---

Zynk will export the data from the "Return summary" report in XML format.  All columns documented below will appear in the output file. 

## Tasks

 * [Export Returns from Peoplevox](export-returns-from-peoplevox)

## Fields
### Return Code

| Type | Example | XML |
| --- | --- | --- |
| string | RET1 | `<Return_code>RET1</Return_code>` |

### Return Date  

| Type | Example | XML |
| --- | --- | --- |
| string | '14/06/2018 16:55:07' | `<Return_date>'14/06/2018 16:55:07'</Return_date>` |

### Quantity  

| Type | Example | XML |
| --- | --- | --- |
| string | 1 | `<Quantity>1</Quantity>` |

### Item Name  

| Type | Example | XML |
| --- | --- | --- |
| string | Sample Product | `<Item_name>Sample Product</Item_name>` |

### Sales Order Number 

| Type | Example | XML |
| --- | --- | --- |
| string | 1234 | `<Sales_order_number>1234</Sales_order_number>` |

### Despatch Date  

| Type | Example | XML |
| --- | --- | --- |
| string | '14/06/2018 16:52:17' | `<Despatch_date></Despatch_date>` |

### Return Reason  

| Type | Example | XML |
| --- | --- | --- |
| string | Not Wanted | `<Return_reason>Not Wanted</Return_reason>` |

### Return Condition  

| Type | Example | XML |
| --- | --- | --- |
| string | NEW | `<Return_condition>NEW</Return_condition>` |

### Return Comments  

| Type | Example | XML |
| --- | --- | --- |
| string | Internal notes:  | `<Return_comments>Internal notes: </Return_comments>` |

### Days Since Despatch

| Type | Example | XML |
| --- | --- | --- |
| string | 237 | `<Days_since_despatch>237</Days_since_despatch>` |

### Item Barcode  

| Type | Example | XML |
| --- | --- | --- |
| string | 5060466510500 | `<Item_barcode>5060466510500</Item_barcode>` |

### Sales Order Contact Name  

| Type | Example | XML |
| --- | --- | --- |
| string | Zynk Software | `<Sales_order_contact_name>Zynk Software</Sales_order_contact_name>` |

### Customer Phone Number  

| Type | Example | XML |
| --- | --- | --- |
| string | 0191 303 7279 | `<Customer_phone_number>0191 303 7279</Customer_phone_number>` |

### Item Sale Price  

| Type | Example | XML |
| --- | --- | --- |
| string | 3.00 | `<Item_sale_price>3.00</Item_sale_price>` |

### Sales Order Email  

| Type | Example | XML |
| --- | --- | --- |
| string | support@zynk.com | `<Sales_order_email>support@zynk.com</Sales_order_email>` |

### Customer Purchase Order Reference Number  

| Type | Example | XML |
| --- | --- | --- |
| string | INT001 | `<Customer_purchase_order_reference_number>INT001</Customer_purchase_order_reference_number>` |

### Channel Name  

| Type | Example | XML |
| --- | --- | --- |
| string | Web | `<Channel_name>Web</Channel_name>` |

### Payment Type  

| Type | Example | XML |
| --- | --- | --- |
| string | Card | `<Payment_type>Card</Payment_type>` |

### Attribute 1  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute1 />` |

### Attribute 2  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute2 />` |

### Attribute 3  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute3 />` |

### Attribute 4  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute4 />` |

### Attribute 5  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute5 />` |

### Attribute 6  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute6 />` |

### Attribute 7  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute7 />` |

### Attribute 8  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute8 />` |

### Attribute 9  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute9 />` |

### Attribute 10  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute10 />` |

### Attribute 11  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute11 />` |

### Attribute 12  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute12 />` |

### Attribute 13  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute13 />` |

### Attribute 14  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute14 />` |

### Attribute 15  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute15 />` |

### Site Reference  

| Type | Example | XML |
| --- | --- | --- |
| string | PrimarySite | `<Site_reference>PrimarySite</Site_reference>` |

### Is Reusable  

| Type | Example | XML |
| --- | --- | --- |
| string | True | `<Is_Reusable>True</Is_Reusable>` |

### Item Code  

| Type | Example | XML |
| --- | --- | --- |
| string | PROD001 | `<Item_code>PROD001</Item_code>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<ReturnsSummary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Return>
    <Return_code>RET1</Return_code>
    <Return_date>'14/06/2018 16:55:07'</Return_date>
    <Quantity>1</Quantity>
    <Item_name>Sample Product</Item_name>
    <Sales_order_number>POO2</Sales_order_number>
    <Despatch_date>'14/06/2018 16:52:17'</Despatch_date>
    <Return_reason>Why Not</Return_reason>
    <Return_condition>NEW</Return_condition>
    <Return_comments>Internal notes: </Return_comments>
    <Days_since_despatch>237</Days_since_despatch>
    <Item_barcode>5060466510500</Item_barcode>
    <Sales_order_contact_name>Zynk Software</Sales_order_contact_name>
    <Customer_phone_number>0191 303 7279</Customer_phone_number>
    <Item_sale_price>3.00</Item_sale_price>
    <Sales_order_email>support@zynk.com</Sales_order_email>
    <Customer_purchase_order_reference_number>INT001</Customer_purchase_order_reference_number>
    <Channel_name>Web</Channel_name>
    <Payment_type>Card</Payment_type>
    <Attribute1 />
    <Attribute2 />
    <Attribute3 />
    <Attribute4 />
    <Attribute5 />
    <Attribute6 />
    <Attribute7 />
    <Attribute8 />
    <Attribute9 />
    <Attribute10 />
    <Attribute11 />
    <Attribute12 />
    <Attribute13 />
    <Attribute14 />
    <Attribute15 />
    <Site_reference>PrimarySite</Site_reference>
    <Is_Reusable>True</Is_Reusable>
    <Item_code>PROD001</Item_code>
  </Return>
</ReturnsSummary>
```
