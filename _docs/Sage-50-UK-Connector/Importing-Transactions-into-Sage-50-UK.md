---
slug: importing-transactions-into-sage-50-uk
redirect_from: "/article/420-importing-transactions-into-sage-50-uk"
title: Importing Transactions into Sage 50 UK
---
This task will any type of audit trail transactions to Sage 50 that is supplied in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Auto Allocate Transactions
_Required_  
Attempt auto-allocation of SR, SA, PA or PP transactions by matching to to an Invoice with the same Account Ref and Reference.

### Prevent Duplicates
_Required_  
Set this to 'True' to check whether the record Id supplied in the input XML file has already been imported, and if so skip the record.

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Transaction XML](sage-50-uk-transaction-xml):  

```xml
<?xml version="1.0"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>631</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>ABS001</AccountReference>
      <CustomerId>232</CustomerId>
      <TransactionDate>2009-03-02T00:00:00</TransactionDate>
      <NominalCode>4000</NominalCode>
      <Department>1</Department>
      <Reference>35</Reference>
      <PaymentReference />
      <Details>AT Mini Tower Case</Details>
      <NetAmount>12.56</NetAmount>
      <TaxCode>1</TaxCode>
      <BankReference>1200</BankReference>
    </Transaction>
  </Transactions>
</Company>
```
