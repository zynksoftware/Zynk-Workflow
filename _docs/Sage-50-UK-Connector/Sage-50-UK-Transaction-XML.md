---
slug: sage-50-uk-transaction-xml
title: Sage 50 UK Transaction XML
---
## Supported Transaction Types
The TransactionType field can be one of the following:
 * SalesInvoice
 * SalesCredit
 * SalesReceiptOnAccount (or SalesReceipt)
 * SalesPayment
 * PurchaseInvoice
 * PurchaseCredit
 * PurchaseReceipt
 * PurchasePaymentOnAccount (or PurchasePayment)
 * BankReceipt
 * BankPayment
 * JournalDebit
 * JournalCredit

## Allocations  
Some credit transaction types can be automatically allocated during the import, we do not support allocating existing credit transactions.  Using the Reference field you can specify the Sage reference of the transaction you want to allocate to, note we can only allocated to a single debit transaction in Sage.  If the reference cannot be found or is already allocated the transaction will be imported, but left unallocated.  As there is potential for the allocation to fail SR transactions will be imported as SA, and PP as PA.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Reference>1</Reference>
    </Transaction>
  </Transactions>
</Company>
```

## Grouping  
Some transactions can be grouped during the import, to end up with a single header transaction in Sage with multiple splits.  With the exception of JournalDebits and JournalCredits all transactions are grouped based on a match of AccountReference, Reference, SecondReference, TransactionDate and TransactionType.  JournalDebits and JournalCredits use the same matching except TransactionType, as the two types are used together to create a single journal.  For transactions to be imported as a group they must appear sequentially in the XML file.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>1</Id>
      <CustomerId>1</CustomerId>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>4000</NominalCode>
      <Reference>1</Reference>
      <Details>4000</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>2</Id>
      <CustomerId>1</CustomerId>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>4001</NominalCode>
      <Reference>1</Reference>
      <Details>4001</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Sales Invoice
Supports grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>1</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>4000</NominalCode>
      <Reference>SI1</Reference>
      <Details>Sales Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>2</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>4001</NominalCode>
      <Reference>SI1</Reference>
      <Details>Sales Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Sales Credit  
Supports grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>3</Id>
      <TransactionType>SalesCredit</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>4000</NominalCode>
      <Reference>SC1</Reference>
      <Details>Sales Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>4</Id>
      <TransactionType>SalesCredit</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>4001</NominalCode>
      <Reference>SC1</Reference>
      <Details>Sales Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Sales Receipt
Supports allocations. Please note that Sage expects a gross amount for Sales Receipt transactions, so it is not valid to provide a TaxAmount in the XML. The gross value should be provided as the NetAmount. 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>5</Id>
      <TransactionType>SalesReceipt</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <BankReference>1200</BankReference>
      <Reference>SI1</Reference>
      <Details>Sales Receipt</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>9</TaxCode>
    </Transaction>
  </Transactions>
</Company>
```

## Sales Payment

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>6</Id>
      <TransactionType>SalesPayment</TransactionType>
      <AccountReference>A1D001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <BankReference>1200</BankReference>
      <Reference>SP1</Reference>
      <Details>Sales Payment</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>0</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Purchase Invoice
Supports grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>7</Id>
      <TransactionType>PurchaseInvoice</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>5000</NominalCode>
      <Reference>PI1</Reference>
      <Details>Purchase Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
      <ProjectRef>PROJ</ProjectRef>
      <ProjectItem>COST</ProjectItem>
    </Transaction>
    <Transaction>
      <Id>8</Id>
      <TransactionType>PurchaseInvoice</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>5001</NominalCode>
      <Reference>PI1</Reference>
      <Details>Purchase Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
      <ProjectRef>PROJ</ProjectRef>
      <ProjectItem>COST</ProjectItem>
    </Transaction>
  </Transactions>
</Company>
```

## Purchase Credit
Supports grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>9</Id>
      <TransactionType>PurchaseCredit</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>5000</NominalCode>
      <Reference>PC1</Reference>
      <Details>Purchase Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
      <ProjectRef>PROJ</ProjectRef>
      <ProjectItem>COST</ProjectItem>
    </Transaction>
    <Transaction>
      <Id>10</Id>
      <TransactionType>PurchaseCredit</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>5001</NominalCode>
      <Reference>PC1</Reference>
      <Details>Purchase Credit</Details>
      <NetAmount>100</NetAmount>
      <TaxRate>20</TaxRate>
      <TaxCode>1</TaxCode>
      <TaxAmount>20</TaxAmount>
      <ProjectRef>PROJ</ProjectRef>
      <ProjectItem>COST</ProjectItem>
    </Transaction>
  </Transactions>
</Company>
```

## Purchase Receipt

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>11</Id>
      <TransactionType>PurchaseReceipt</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <BankReference>1200</BankReference>
      <Reference>PR1</Reference>
      <Details>Purchase Receipt</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>0</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Purchase Payment
Supports allocations.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>12</Id>
      <TransactionType>PurchasePayment</TransactionType>
      <AccountReference>CON001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <BankReference>1200</BankReference>
      <Reference>PI1</Reference>
      <Details>Purchase Payment</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>0</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Bank Receipt  

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>13</Id>
      <TransactionType>BankReceipt</TransactionType>
      <AccountReference>1200</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>7000</NominalCode>
      <Reference>BR1</Reference>
      <Details>Bank Receipt</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>0</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Bank Payment  

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>14</Id>
      <TransactionType>BankPayment</TransactionType>
      <AccountReference>1200</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <NominalCode>7000</NominalCode>
      <Reference>BP1</Reference>
      <Details>Bank Payment</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>0</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```

## Journal Debit / Credit
Supports grouping.  Note all values must be positive

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>15</Id>
      <TransactionType>JournalDebit</TransactionType>
      <AccountReference>4000</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <Reference>JDC1</Reference>
      <Details>Journal Debit</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
    <Transaction>
      <Id>16</Id>
      <TransactionType>JournalCredit</TransactionType>
      <AccountReference>4001</AccountReference>
      <TransactionDate>2014-04-22T00:00:00</TransactionDate>
      <Reference>JDC1</Reference>
      <Details>Journal Credit</Details>
      <NetAmount>240</NetAmount>
      <TaxRate>0</TaxRate>
      <TaxCode>9</TaxCode>
      <TaxAmount>0</TaxAmount>
    </Transaction>
  </Transactions>
</Company>
```
