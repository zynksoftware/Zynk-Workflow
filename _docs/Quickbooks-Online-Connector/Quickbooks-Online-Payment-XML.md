---
slug: quickbooks-online-payment-xml
title: Quickbooks Online Payment XML
---
The Upload Payments task allows you to create and update payments in QuickBooks. Any fields not documented below are not currently supported by our upload.

Sample import file for creating a basic payment:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPayment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPayment>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <CustomerRef name="Zynk Software"></CustomerRef>
      <TotalAmt>50</TotalAmt>
    </Data>
  </RecordOfPayment>
</ArrayOfPayment>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a payment. The whole structure from the root element down is shown in the samples below as a reference of where elements should appear in the object model.

## Payment Details

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Optional | Used for matching to existing payments. |
| ExternalId | - | 6492 | string | 255 | Optional | Used for matching to existing payments. The value provided will be stored in Zynk's truth table, and used to lookup the Id of the customer. |
| CustomerRef | Customer | 1 | integer | - | Required | If you don't know the customer ID, you can specify their display name using the name attribute, and the task will perform a lookup. |
| TxnDate | Payment Date | 2016-07-15 | date | - | Optional | Defaults to the current date if not specified. |
| PaymentMethodRef | Payment Method | 1 | integer | - | Optional | If you don't know the payment method ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| PaymentRefNum | Reference No. | PC3452DX | string | 21 | Optional |
| DepositToAccountRef | Deposit To | 1 | integer | - | Optional | If you don't know the account ID, you can specify the name using the name attribute, and the task will perform a lookup. The chosen account must have type 'Other Current Asset' or 'Bank'. Defaults to the undeposited funds account if not specified. |
| TotalAmt | Amount Received | 50 | decimal | - | Required |
| ExchangeRate | - | 1.25 | decimal | - | Optional | Defaults to 1 if not specified. |
| PrivateNote | Memo | Sample memo | string | 4000 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPayment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPayment>
    <ExternalId>1234</ExternalId>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <Id>1234</Id>
      <CustomerRef name="Zynk Software">1</CustomerRef>
      <TxnDate>2016-07-15</TxnDate>
      <PaymentMethodRef name="Card">1</PaymentMethodRef>
      <PaymentRefNum>PC3452DX</PaymentRefNum>
      <DepositToAccountRef name="Current">1</DepositToAccountRef>
      <TotalAmt>50</TotalAmt>
      <ExchangeRate>1</ExchangeRate>
      <PrivateNote>Sample memo</PrivateNote>
    </Data>
  </RecordOfPayment>
</ArrayOfPayment>
```

## Payment Lines
You can optionally provide a one or more lines, which represent the outstanding transactions you want to link the payment to. If you don't provide any lines, the payment will automatically be linked to the oldest outstanding transaction(s).

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Amount | Payment | 50 | integer | - | Required |
| LinkedTxn > TxnId | Description | 1 | string | 15 | Dependant | Required if TxnLineId is specified. Used in conjuction with TxnType to specify the transaction the payment is to be linked to. |
| LinkedTxn > TxnType | Description | Invoice | enum | - | Dependant | Required if TxnLineId is specified. Used in conjuction with TxnId to specify the transaction the payment is to be linked to. Allowed values are Invoice, CreditMemo, JournalEntry, CreditCardCredit, Check and Expense. |
| LinkedTxn > TxnLineId | - | 1 | string | 15 | Optional | The line number of a specific line of the linked transaction. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfPayment xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfPayment>
    <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
      <Line>
        <Amount>50</Amount>
        <LinkedTxn>
          <TxnId>1</TxnId>
          <TxnType>Invoice</TxnType>
          <TxnLineId>1</TxnLineId>
        </LinkedTxn>
      </Line>
    </Data>
  </RecordOfPayment>
</ArrayOfPayment>
```