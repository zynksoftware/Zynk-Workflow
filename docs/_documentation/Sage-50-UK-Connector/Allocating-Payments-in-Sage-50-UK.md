---
slug: allocating-payments-in-sage-50-uk
redirect_from: "/article/390-allocating-payments-in-sage-50-uk"
title: Allocating Payments in Sage 50 UK
---
This task will attempt to allocate transactions in Sage based on the selected options. It will export a list of successfully allocated transactions in Zynk XML format.

## Settings
### Allow Partial Allocations
_Required_  
If True will check the outstanding gross amount of splits match before allocating.

### Automatically Allocate Credit Notes
_Required_  
If True will include Credit Note transactions when trying to allocate payments.

### Date From
_Required_  
Used with Date To, allows you to only attempt to allocate transactions created between the specified time frame.

### Date To
_Required_  
Used with Date From, allows you to only attempt to allocate transactions created between the specified time frame.

### Ledger Type
_Required_  
Choose the ledger type to allocate, either Sales or Purchase.

### Match Transaction Amount
_Required_  
If True will check the gross amount of the transactions match before allocating.

### Match Transaction Reference
_Required_  
If True will only allocate transactions which have a matching reference.

### Only Check Zero Balance Accounts
_Required_  
If True will only allocate transactions that are associated with accounts with a zero balance.

### Skip Accounts with Unallocated Credits
_Required_  
If True will ignore accounts that have unallocated transactions.

### Output File
_Required_  
The file to save the list of successfully allocated transactions to.

### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample output file is shown below, which shows the SA transaction with reference 24 was allocated to the SI transaction with reference 24.

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Transactions>
    <Transaction>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>JOE001</AccountReference>
      <TransactionDate>2016-01-27T00:00:00</TransactionDate>
      <PostedDate xsi:nil="true" />
      <AnalysisCode />
      <NominalCode />
      <Reference>24</Reference>
      <Details />
      <NetAmount>170.21</NetAmount>
      <TaxRate xsi:nil="true" />
      <TaxCode xsi:nil="true" />
      <TaxAmount>29.79</TaxAmount>
      <ElectronicTransaction xsi:nil="true" />
      <OutstandingAmount xsi:nil="true" />
      <TransactionNumber>14</TransactionNumber>
      <BankReference />
      <Discount xsi:nil="true" />
      <ExchangeRate xsi:nil="true" />
      <VatInclusive xsi:nil="true" />
      <CustomFields />
    </Transaction>
    <Transaction>
      <TransactionType>SalesReceiptOnAccount</TransactionType>
      <AccountReference>JOE001</AccountReference>
      <TransactionDate>2016-02-03T00:00:00</TransactionDate>
      <PostedDate xsi:nil="true" />
      <AnalysisCode />
      <NominalCode />
      <Reference>24</Reference>
      <Details />
      <NetAmount>-200</NetAmount>
      <TaxRate xsi:nil="true" />
      <TaxCode xsi:nil="true" />
      <TaxAmount>0</TaxAmount>
      <ElectronicTransaction xsi:nil="true" />
      <OutstandingAmount xsi:nil="true" />
      <TransactionNumber>15</TransactionNumber>
      <BankReference />
      <Discount xsi:nil="true" />
      <ExchangeRate xsi:nil="true" />
      <VatInclusive xsi:nil="true" />
      <CustomFields />
    </Transaction>
  </Transactions>
</Company>
```