---
slug: sage-50-uk-transaction-xml
title: Sage 50 UK Transaction XML
---

Zynk supports importing and exporting most transaction types supported in Sage 50 UK including sales, purchase, bank and journals.

The same tasks and object model are used for all transctions types, however certain fields are only valid for certain types.  See below for details on which fields are supported per type.

## Tasks
 * [Exporting Transactions from Sage 50 UK](exporting-transactions-from-sage-50-uk)
 * [Importing Transactions into Sage 50 UK](importing-transactions-into-sage-50-uk)

## Transaction Types
The following transaction types are supported by our tasks: -

 * [BR - Bank Receipt](http://workflow.zynk.com/sage-50-uk-transaction-xml#br---bank-receipt)
 * [BP - Bank Payment](http://workflow.zynk.com/sage-50-uk-transaction-xml#bp---bank-payment)
 * [JD / JC - Bank Transfer](http://workflow.zynk.com/sage-50-uk-transaction-xml#jd--jc---bank-transfer)
 * [JD / JC - Journal Debit & Journal Credit](http://workflow.zynk.com/sage-50-uk-transaction-xml#jd--jc---journal-debit--journal-credit)
 * [SI - Sales Invoice](http://workflow.zynk.com/sage-50-uk-transaction-xml#si---sales-invoice)
 * [SC - Sales Credit Note](http://workflow.zynk.com/sage-50-uk-transaction-xml#sc---sales-credit-note)
 * [SA - Sales Receipt on Account (or SR - Sales Receipt)](http://workflow.zynk.com/sage-50-uk-transaction-xml#sa---sales-receipt-on-account-or-sr---sales-receipt)
 * [SP - Sales Payment](http://workflow.zynk.com/sage-50-uk-transaction-xml#sp---sales-payment)
 * [PI - Purchase Invoice](http://workflow.zynk.com/sage-50-uk-transaction-xml#pi---purchase-invoice)
 * [PC - Purchase Credit Note](http://workflow.zynk.com/sage-50-uk-transaction-xml#pc---purchase-credit-note)
 * [PA - Purchase Payment on Account (or PP - Purchase Payment)](http://workflow.zynk.com/sage-50-uk-transaction-xml#pa---purchase-payment-on-account-or-pp---purchase-payment)
 * [PR - Purchase Receipt](http://workflow.zynk.com/sage-50-uk-transaction-xml#pr---purchase-receipt)

## Allocations  
If the [Auto Allocate Transactions](http://workflow.zynk.com/importing-transactions-into-sage-50-uk#auto-allocate-transactions) setting is enabled Zynk will attempt to allocate certain transaction types during the import. Only SC, SA (or SR), PC and PA (or PP) transaction types will be used for the auto allocate routine.

Zynk will use the Reference field from our XML (Ref field in Sage) to look up the transaction to allocate to. We only support allocating to a single transaction. If a related transaction cannot be found the transaction will be left unallocated.

As there is potential for the allocation to fail Zynk will always import SR transactions as SA and PP transactions as PA so you can manually allocate in Sage if required.

If you have existing debit and credit transactions you need to allocate see the [Allocating Payments in Sage 50 UK](allocating-payments-in-sage-50-uk) task.

## Grouping  
During the import certain transactions will be grouped, to end up with a single header transaction in Sage with multiple splits. For related transactions to be imported as a group they must appear sequentially in the XML file.

SI, SC, PI and PC transaction types will be grouped where the AccountReference, Reference, SecondReference, TransactionDate and TransactionType XML fields match. You can provide as many transactions as you need in the XML to represent the required splits.

JD and JC transaction types will be grouped where the AccountReference, Reference, SecondReference and TransactionDate XML fields match, as the two types are used together to create a single journal. You can provide as many transactions as you need in the XML to represent the required journals, as long as there is at least one of each type.

## Duplicate Prevention
If the [Prevent Duplicates](http://workflow.zynk.com/importing-transactions-into-sage-50-uk#prevent-duplicates) setting is enabled Zynk will check to see if the Id provided in the XML has already been imported. If the record has already been processed it will be skipped, and output to the Fail File.

## BR - Bank Receipt
This will create a transaction against the activity of the specified bank account, the same as manually entering using Bank Accounts -> Bank Receipts in Sage.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 1 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | BankReceipt | - | Enum | Required |
| Bank | AccountReference | 1200 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | BR1 | 10 | String | Optional |
| Ex.Ref | PaymentReference | 1 | 10 | String | Optional |
| N/C | NominalCode | 7000 | 4 | String | Required |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Project Ref | ProjectRef | PRJ1 | 8 | String | Optional |
| Details | Details | Bank Receipt | 60 | String | Optional |
| Net | NetAmount | 240 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>1</Id>
      <TransactionType>BankReceipt</TransactionType>
      <AccountReference>1200</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <Reference>BR1</Reference>
      <PaymentReference>1</PaymentReference>
      <NominalCode>7000</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <Details>Bank Receipt</Details>
      <NetAmount>240</NetAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## BP - Bank Payment
This will create a transaction against the activity of the specified bank account, the same as manually entering using Bank Accounts -> Bank Payments in Sage.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 2 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | BankPayment | - | Enum | Required |
| Bank | AccountReference | 1200 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | BP1 | 10 | String | Optional |
| Ex.Ref | PaymentReference | 2 | 10 | String | Optional |
| N/C | NominalCode | 7000 | 4 | String | Required |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Project Ref | ProjectRef | PRJ1 | 8 | String | Optional |
| Code Code | ProjectItem | LAB1 | 8 | String | Optional |
| Details | Details | Bank Payment | 60 | String | Optional |
| Net | NetAmount | 240 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>2</Id>
      <TransactionType>BankPayment</TransactionType>
      <AccountReference>1200</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <Reference>BP1</Reference>
      <PaymentReference>2</PaymentReference>
      <NominalCode>7000</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <ProjectItem>LAB1</ProjectItem>
      <Details>Bank Payment</Details>
      <NetAmount>240</NetAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## JD / JC - Bank Transfer
This will create a set of journals to transfer balances between bank accounts, the same as manually entering using Bank Accounts -> Bank Transfer.

During the import Zynk will validate the debits and credits in the journal set balance.  If there is a variance and the [Journal Variance Nominal Code](http://workflow.zynk.com/importing-transactions-into-sage-50-uk#prevent-duplicates) setting has a valid nominal an additional balancing transaction will be created, otherwise the whole set will be rejected.

If either of the bank accounts provided are not in the base currency of the company being imported into and an exchange rate is not provided Zynk will read the exchange rates configured in Sage.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 3 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | BankTransfer | - | Enum | Required |
| Bank | FromBankAccount | 1200 | 8 | String | Required |
| Bank | ToBankAccount | 1260 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | BT1 | 10 | String | Required |
| Ex.Ref | PaymentReference | 3 | 10 | String | Optional |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Details | Details | Journal Debit | 60 | String | Optional |
| Net | PaymentAmount | 100 | 8 | Double | Required |
| Net | ReceiptAmount | 150 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |
| Exchange rate | ExchangeRate | 1.5 | 8 | Double | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>3</Id>
      <TransactionType>BankTransfer</TransactionType>
      <FromBankAccount>1200</FromBankAccount>
      <ToBankAccount>1260</ToBankAccount>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <Reference>BT1</Reference>
      <PaymentReference>3</PaymentReference>
      <Department>1</Department>
      <Fund>001</Fund>
      <Details>Bank Transfer</Details>
      <PaymentAmount>100</PaymentAmount>
      <ReceiptAmount>150</ReceiptAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
      <ExchangeRate>1.5</ExchangeRate>
    </Transaction>
  </Transactions>
</Company>
```

## JD / JC - Journal Debit & Journal Credit
This will create a set of journals to transfer balances between nominal codes, the same as manually entering using Nominal Codes -> Journal Entry.

During the import Zynk will validate the debits and credits in the journal set balance.  If there is a variance and the [Journal Variance Nominal Code](http://workflow.zynk.com/importing-transactions-into-sage-50-uk#prevent-duplicates) setting has a valid nominal an additional balancing transaction will be created, otherwise the whole set will be rejected.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 4 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | JournalDebit / JournalCredit | - | Enum | Required |
| Bank | AccountReference | 4000 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | JDC1 | 10 | String | Required |
| Ex.Ref | PaymentReference | 4 | 10 | String | Optional |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Details | Details | Journal Debit | 60 | String | Optional |
| Net | NetAmount | 240 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
      <Transaction>
      <Id>4</Id>
      <TransactionType>JournalDebit</TransactionType>
      <AccountReference>4000</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <Reference>JDC1</Reference>
      <PaymentReference>4</PaymentReference>
      <Department>1</Department>
      <Fund>001</Fund>
      <Details>Journal Debit</Details>
      <NetAmount>240</NetAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>5</Id>
      <TransactionType>JournalCredit</TransactionType>
      <AccountReference>4001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <Reference>JDC1</Reference>
      <PaymentReference>5</PaymentReference>
      <Department>1</Department>
      <Fund>001</Fund>
      <Details>Journal Credit</Details>
      <NetAmount>240</NetAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## SI - Sales Invoice
This will create a transaction against the activity of the specified customer account, the same as manually entering using Customers -> Batch Invoice in Sage. SI transactions support grouping during the import.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 6 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | SalesInvoice | - | Enum | Required |
| Account | AccountReference | A1D001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Due Date | DueDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | SI1 | 10 | String | Optional |
| Ex.Ref | PaymentReference | 6 | 10 | String | Optional |
| N/C | NominalCode | 4000 | 4 | String | Required |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Project Ref | ProjectRef | PRJ1 | 8 | String | Optional |
| Details | Details | Sales Invoice | 60 | String | Optional |
| Net | NetAmount | 100 | 8 | Double | Required |
| T/C | TaxCode | 1 | 2 | Int | Optional |
| Tax | TaxAmount | 20 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>6</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>SI1</Reference>
      <PaymentReference>6</PaymentReference>
      <NominalCode>4000</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <Details>Sales Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>7</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>SI1</Reference>
      <PaymentReference>6</PaymentReference>
      <NominalCode>4001</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <Details>Sales Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## SC - Sales Credit Note
This will create a transaction against the activity of the specified customer account, the same as manually entering using Customers -> Batch Credit in Sage. SC transactions support grouping during the import, and can be auto allocated.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 8 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | SalesCredit | - | Enum | Required |
| Account | AccountReference | A1D001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Due Date | DueDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | SC1 | 10 | String | Required for allocations, the Ref of the transaction to allocate to |
| Ex.Ref | PaymentReference | 8 | 10 | String | Optional |
| N/C | NominalCode | 4000 | 4 | String | Required |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Project Ref | ProjectRef | PRJ1 | 8 | String | Optional |
| Details | Details | Sales Credit | 60 | String | Optional |
| Net | NetAmount | 100 | 8 | Double | Required |
| T/C | TaxCode | 1 | 2 | Int | Optional |
| Tax | TaxAmount | 20 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>8</Id>
      <TransactionType>SalesCredit</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>SI1</Reference>
      <PaymentReference>8</PaymentReference>
      <NominalCode>4000</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <Details>Sales Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>9</Id>
      <TransactionType>SalesCredit</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>SI1</Reference>
      <PaymentReference>8</PaymentReference>
      <NominalCode>4001</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <Details>Sales Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## SA - Sales Receipt on Account (or SR - Sales Receipt)
This will create a transaction against the activity of the specified customer account, the same as manually entering using Customers -> Customer Receipt in Sage. SA transactions support allocation during the import, as there is potential for the allocation to fail Zynk will always import SR transactions as SA so you can manually allocate in Sage if required.

It will depend on the settings in Sage 50, but typically the NetAmount field should be the gross value of the receipt, and use the non-vatable code T9.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 10 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | SalesReceiptOnAccount | - | Enum | Required |
| Account | AccountReference | A1D001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Nominal / Bank | BankReference | 1200 | 8 | String | Required |
| Ref | Reference | SI1 | 10 | String | Required for allocations, the Ref of the transaction to allocate to |
| Ex.Ref | PaymentReference | 8 | 10 | String | Optional |
| Details | Details | Sales Receipt | 60 | String | Optional |
| Net | NetAmount | 240 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>10</Id>
      <TransactionType>SalesReceiptOnAccount</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <BankReference>1200</BankReference>
      <Reference>SI1</Reference>
      <PaymentReference>10</PaymentReference>
      <Details>Sales Receipt</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>9</TaxCode>
    </Transaction>
  </Transactions>
</Company>
```

## SP - Sales Payment
This will create a transaction against the activity of the specified customer account, the same as manually entering using Customers -> Refund in Sage.

It will depend on the settings in Sage 50, but typically the NetAmount field should be the gross value of the receipt, and use the non-vatable code T9.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 11 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | SalesPayment | - | Enum | Required |
| Account | AccountReference | A1D001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Nominal / Bank | BankReference | 1200 | 8 | String | Required |
| Ref | Reference | SP1 | 10 | String | Optional |
| Ex.Ref | PaymentReference | 11 | 10 | String | Optional |
| Details | Details | Sales Payment | 60 | String | Optional |
| Net | NetAmount | 240 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>11</Id>
      <TransactionType>SalesPayment</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <BankReference>1200</BankReference>
      <Reference>SP1</Reference>
      <PaymentReference>11</PaymentReference>
      <Details>Sales Payment</Details>
      <NetAmount>240</NetAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## PI - Purchase Invoice
This will create a transaction against the activity of the specified supplier account, the same as manually entering using Suppliers -> Batch Invoice in Sage. PI transactions support grouping during the import.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 12 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | PurchaseInvoice | - | Enum | Required |
| Account | AccountReference | CON001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Due Date | DueDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | PI1 | 10 | String | Optional |
| Ex.Ref | PaymentReference | 12 | 10 | String | Optional |
| N/C | NominalCode | 5000 | 4 | String | Required |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Project Ref | ProjectRef | PRJ1 | 8 | String | Optional |
| Code Code | ProjectItem | LAB1 | 8 | String | Optional |
| Details | Details | Purchase Invoice | 60 | String | Optional |
| Net | NetAmount | 100 | 8 | Double | Required |
| T/C | TaxCode | 1 | 2 | Int | Optional |
| Tax | TaxAmount | 20 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>12</Id>
      <TransactionType>PurchaseInvoice</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>PI1</Reference>
      <PaymentReference>12</PaymentReference>
      <NominalCode>5000</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <ProjectItem>LAB1</ProjectItem>
      <Details>Purchase Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>13</Id>
      <TransactionType>PurchaseInvoice</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>PI1</Reference>
      <PaymentReference>12</PaymentReference>
      <NominalCode>5001</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <ProjectItem>LAB1</ProjectItem>
      <Details>Purchase Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## PC - Purchase Credit Note
This will create a transaction against the activity of the specified supplier account, the same as manually entering using Suppliers -> Batch Credit in Sage. PC transactions support grouping during the import, and can be auto allocated.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 14 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | PurchaseCredit | - | Enum | Required |
| Account | AccountReference | CON001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Due Date | DueDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Ref | Reference | PC1 | 10 | String | Optional |
| Ex.Ref | PaymentReference | 14 | 10 | String | Optional |
| N/C | NominalCode | 5000 | 4 | String | Required |
| Dept | Department | 1 | 3 | Int | Optional |
| Fund | Fund | 001 | 3 | Int | Optional |
| Project Ref | ProjectRef | PRJ1 | 8 | String | Optional |
| Code Code | ProjectItem | LAB1 | 8 | String | Optional |
| Details | Details | Purchase Credit | 60 | String | Optional |
| Net | NetAmount | 100 | 8 | Double | Required |
| T/C | TaxCode | 1 | 2 | Int | Optional |
| Tax | TaxAmount | 20 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>14</Id>
      <TransactionType>PurchaseCredit</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>PC1</Reference>
      <PaymentReference>14</PaymentReference>
      <NominalCode>5000</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <ProjectItem>LAB1</ProjectItem>
      <Details>Purchase Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>15</Id>
      <TransactionType>PurchaseCredit</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <DueDate>2019-05-16T00:00:00</DueDate>
      <Reference>PC1</Reference>
      <PaymentReference>14</PaymentReference>
      <NominalCode>5001</NominalCode>
      <Department>1</Department>
      <Fund>001</Fund>
      <ProjectRef>PRJ1</ProjectRef>
      <ProjectItem>LAB1</ProjectItem>
      <Details>Purchase Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## PA - Purchase Payment on Account (or PP - Purchase Payment)
This will create a transaction against the activity of the specified supplier account, the same as manually entering using Suppliers -> Supplier Payment in Sage. PA transactions support allocation during the import, as there is potential for the allocation to fail Zynk will always import PP transactions as PA so you can manually allocate in Sage if required.

It will depend on the settings in Sage 50, but typically the NetAmount field should be the gross value of the receipt, and use the non-vatable code T9.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 16 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | PurchasePaymentOnAccount | - | Enum | Required |
| Account | AccountReference | CON001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Nominal / Bank | BankReference | 1200 | 8 | String | Required |
| Ref | Reference | PI1 | 10 | String | Required for allocations, the Ref of the transaction to allocate to |
| Ex.Ref | PaymentReference | 16 | 10 | String | Optional |
| Details | Details | Purchase Payment | 60 | String | Optional |
| Net | NetAmount | 240 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>16</Id>
      <TransactionType>PurchasePaymentOnAccount</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <BankReference>1200</BankReference>
      <Reference>PI1</Reference>
      <PaymentReference>16</PaymentReference>
      <Details>Purchase Payment</Details>
      <NetAmount>240</NetAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## PR - Purchase Receipt
This will create a transaction against the activity of the specified supplier account, the same as manually entering using Suppliers -> Refund in Sage.

It will depend on the settings in Sage 50, but typically the NetAmount field should be the gross value of the receipt, and use the non-vatable code T9.

### XML Fields

| Sage Field | XML Field  | Example  | Field Length  | Field Type  | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 17 | 8 | Int | Required if needed for duplicate prevention |
| Type | TransactionType | PurchaseReceipt | - | Enum | Required |
| Account | AccountReference | CON001 | 8 | String | Required |
| Date | TransactionDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Posted Date | PostedDate | 2019-05-16T00:00:00 | - | Datetime | Optional |
| Nominal / Bank | BankReference | 1200 | 8 | String | Required |
| Ref | Reference | PR1 | 10 | String | Optional |
| Ex.Ref | PaymentReference | 17 | 10 | String | Optional |
| Details | Details | Purchase Receipt | 60 | String | Optional |
| Net | NetAmount | 240 | 8 | Double | Required |
| T/C | TaxCode | 9 | 2 | Int | Optional |
| Tax | TaxAmount | 0 | 8 | Double | Optional |

### Sample XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>17</Id>
      <TransactionType>PurchaseReceipt</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2019-05-16T00:00:00</TransactionDate>
      <PostedDate>2019-05-16T00:00:00</PostedDate>
      <BankReference>1200</BankReference>
      <Reference>PR1</Reference>
      <PaymentReference>17</PaymentReference>
      <Details>Purchase Receipt</Details>
      <NetAmount>240</NetAmount>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```
