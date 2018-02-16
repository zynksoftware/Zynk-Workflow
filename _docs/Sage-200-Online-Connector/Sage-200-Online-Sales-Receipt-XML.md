---
slug: sage-200-online-sales-receipt-xml
title: Sage 200 Online Sales Receipt XML
---
Receipts are used to record a sales receipt against a particular customer's account.  Uploading a sales receipt will create a posted transaction, to download receipts see [Exporting Sales Transactions from Sage 200 Online](exporting-sales-transactions-from-sage-200-online) which will bring data back in [Sage 200 Online Sales Transaction XML](sage-200-online-sales-transaction-xml) format. Further information can be found on the [Sage 200 Online Sales Receipts API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200/accounts/v1/sales_receipts).

## Tasks
 * [Exporting Sales Transactions from Sage 200 Online](exporting-sales-transactions-from-sage-200-online)
 * [Importing Sales Receipts to Sage 200 Online](importing-sales-receipts-to-sage-200-online)

## Identifiers
### external_id
_Optional (recommended)_  
To prevent duplicates sales receipts being imported into Sage 200 we would recommend to always set the external_id field to a unique id from the source system.  When the field is provided it will be stored within Zynks internal database along with the URN assigned by Sage 200.

| Type | Example | XML |
| --- | --- | --- |
| string(255) | 12345 | `<external_id>12345</external_id>` |

## Fields for Download and Upload
### customer_id
_Dependant (see [customer](#customer))_  
Customer record Id, can also be set using customer reference, see [customer](#customer).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27006 | `<customer_id>27006</customer_id>` |

### bank_id
_Dependant (see [bank](#bank))_  
Bank record Id, can also be set using bank code, see [bank](#bank).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 1 | `<bank_id>1</bank_id>` |

### cheque_value
_Required_  
Value of the receipt.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 120 | `<cheque_value>120</cheque_value>` |

### cheque_currency_id
_Optional (see [cheque_currency](#cheque_currency))_  
Receipt currency record Id, can also be set using cheque currency code, see [cheque_currency](#cheque_currency).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 1 | `<cheque_currency_id>1</cheque_currency_id>` |

### customer_cheque_value
_Optional_  
Value to post to the customer account

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 120 | `<customer_cheque_value>120</customer_cheque_value>` |

### transaction_date
_Optional_  
Transaction date.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-02T00:00:00| `<transaction_date>2017-06-02T00:00:00</transaction_date>` |

### exchange_rate
_Optional_  
Exchange rate for the receipt.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 6dp) | 1.000000 | `<exchange_rate>1.000000</exchange_rate>` |

### settlement_discount_value
_Optional_  
Settlement discount value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0 | `<settlement_discount_value>0</settlement_discount_value>` |

### reference
_Optional_  
Receipt reference.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | Web Sales | `<reference>Web Sales</reference>` |

### second_reference
_Optional_  
Receipt second reference.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | Order #12345 | `<second_reference>Order #12345</second_reference>` |

### nominal_analysis_items
_Optional_  
Nominal analysis lines.  The `<nominal_analysis_items>` node is a collection of `<nominal_analysis_item>` nodes that allow you analyse the value of the sales receipt to specific nominal codes.  See full example XML below.

#### code
_Required_  
Nominal account code.

| Type | Example | XML |
| --- | --- | --- |
| string(8) | 4000 | `<code>4000</code>` |

#### cost_centre
_Optional_  
Cost centre. If specified must correspond to the code.

| Type | Example | XML |
| --- | --- | --- |
| string(3) | 020 | `<cost_centre>020</cost_centre>` |

#### department
_Optional_  
Department. If specified must correspond to the code.

| Type | Example | XML |
| --- | --- | --- |
| string(3) | SAL | `<department>SAL</department>` |

#### value
_Optional_  
Value to post to the nominal account.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 120 | `<value>120</value>` |

## Expandable Fields
Related information linked to sales receipts are also included in the downloaded XML, these can also be used to set certain fields on sales receipt uploads using lookups rather than needing to know the internal id of the related record.

### customer
_Dependant (see [customer_id](#customer_id))_  
The sales receipts customer.  On an upload you can set the reference of the customer to use for the sales receipt and Zynk will lookup the correct internal id from Sage.

#### Upload example using the reference

```xml
<customer>
    <reference>ZYNK001</reference>
</customer>
```

### bank
_Dependant (see [bank_id](#bank_id))_  
The sales receipts bank.  On an upload you can set the code of the bank to use for the sales receipt and Zynk will lookup the correct internal id from Sage.

#### Upload example using the code

```xml
<bank>
    <code>DEFAULT</code>
</bank>
```

### cheque_currency
_Optional (see [cheque_currency_id](#cheque_currency_id))_  
The cheque currency of the receipt.  On an upload you can set the code of the currency to use for the sales receipt and Zynk will lookup the correct internal id from Sage.

#### Upload example using the code

```xml
<cheque_currency>
    <code>GBP</code>
</cheque_currency>
```

## Example XML
### Minimal Example

```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesReceipts 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SalesReceipt>
        <cheque_value>120</cheque_value>
        <bank>
            <code>DEFAULT</code>
        </bank>
        <customer>
            <reference>ZYNK001</reference>
        </customer>
    </SalesReceipt>
</SalesReceipts>
```

### Full Example

```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesReceipts 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SalesReceipt>
        <external_id>12345</external_id>
        <customer_id>27006</customer_id>
        <cheque_value>120</cheque_value>
        <cheque_currency_id>1</cheque_currency_id>
        <customer_cheque_value>120</customer_cheque_value>
        <transaction_date>2017-06-02T00:00:00</transaction_date>
        <exchange_rate>1.000000</exchange_rate>
        <settlement_discount_value>0</settlement_discount_value>
        <reference>Web Sales</reference>
        <second_reference>Order #12345</second_reference>
        <bank>
            <code>DEFAULT</code>
        </bank>
        <customer>
            <reference>ZYNK001</reference>
        </customer>
        <cheque_currency>
            <code>GBP</code>
        </cheque_currency>
        <nominal_analysis_items>
            <nominal_analysis_item>
                <code>4000</code>
                <cost_centre>020</cost_centre>
                <department>SAL</department>
                <value>120</value>
            </nominal_analysis_item>
        </nominal_analysis_items>
    </SalesReceipt>
</SalesReceipts>
```
