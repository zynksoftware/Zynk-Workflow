---
slug: sage-200-transaction-xml
title: Sage 200 Transaction XML
---
Import Transactions allows you to create new transactions in Sage 200, and optionally allocate to existing transactions.  We recommend that the Id field be populated by the unique id of the transactions from the external system, Zynk uses this field to track transactions already imported to prevent duplicates being created in Sage.   

Any Sage fields not documented below are not directly supported with our imports.

| XML Field  | Sage Field  | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
|  Id | N/A  | 1 | string | 255 | Optional |
| TransactionType* | Trans. Type | SalesInvoice | enum | - | Required |
| CustomerId* | A/C ref  | 1 | string | 255 | Required for sales and purchase transaction types, unless an AccountReference is provided |
| AccountReference | A/C ref  | ANDREW | string | 8 | Required for sales and purchase transaction types, unless a CustomerId is provided |
| TransactionDate  | Trans. Date  | 2011-01-01T11:11:11 | dateTime | - | Optional |
| DueDate | Due Date  | 2011-01-01T11:11:11 | dateTime | - | Optional |
| NominalCode  | Nominal A/C No.  | 4000 | string | 8 | Optional |
| CostCentre  | Nominal CC  | 01 | string | 3 | Optional |
| Department  | Nominal Dept.  | 01 | string | 3 | Optional |
| ProjectRef  | Project  | string | Optional |
| ProjectItem  | Project Item  | string | Optional |
| Reference  | Reference  | SI1 | string | 20 | Optional |
| SecondReference  | 2nd Reference  | Order 1 | string | 20 | Optional |
| Details | Narrative | Sales Invoice | string | - | Optional |
| NetAmount  | Net Value  | 100 | double | - | Required |
| TaxAmount  | Tax Value  | 20 | double | - | Optional |
| TaxCode* | Tax Code  | 1 | int | - | Optional |
| TaxRate* |  N/A | 20 | double | - | Optional |
| AnalysisCode* | Transaction Analysis  | AC1 | string | 20 | Optional |
| VatInclusive* |  N/A | false | bool | - | Optional |
| BankReference |  Bank A/C Ref. | string | 8 | Optional |
| DiscountValue  |  Discount | 0 | double | - | Optional |
| QueryFlag  |  Query | T | string | 1 | Optional |
| ExchangeRate* | Exchange Rate | 1.145 | double | - | Optional |

*   TransactionType* - See supported types below
*   CustomerId* - The A/C Ref can be looked up based on CustomerId if the customer or supplier was imported into Sage using Zynk, and an Id was provided at the time of import.
*   DueDate - If not specified, the due date will be set automatically based on the customer's payment terms.
*   TaxCode* - Defaults to trader default if not provided. Tax can't be applied to SalesReceipt, SalesPayment, PurchaseReceipt, PurchasePayment, JournalCredit and JournalDebit transactions, the exempt tax code will always be used.

*   TaxRate* - Defaults to the rate associated with the TaxCode
*   AnalysisCode* - Only imported if configured within Sage 200
*   VatInclusive* - Used to net down the transaction if required
*   ExchangeRate* - Will use the exchange rate configured in Sage for the currency associated with the customer account if not provided

Sample import file for creating a sales invoice transaction:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>1</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate>
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>SI1</Reference>
      <SecondReference>Order 1</SecondReference>
      <Details>Sales Invoice</Details>
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode>
      <TaxRate>20</TaxRate>
      <AnalysisCode>AC1</AnalysisCode>
      <QueryFlag>T</QueryFlag>
      <ExchangeRate>1.145</ExchangeRate>
    </Transaction>
  </Transactions>
</Company>
```

## Supported Transaction Types
The TransactionType field can be one of the following:

*   SalesInvoice
*   SalesCredit
*   SalesReceipt
*   SalesPayment
*   PurchaseInvoice
*   PurchaseCredit
*   PurchaseReceipt
*   PurchasePayment
*   BankReceipt
*   BankPayment
*   BankNonTaxableReceipt (Zynk v2.5+)
*   BankNonTaxablePayment (Zynk v2.5+)
*   JournalDebit
*   JournalCredit
*   ProjectCostOpeningBalance
*   ProjectRevenueOpeningBalance
*   ProjectCostAdjustment
*   ProjectRevenueAdjustment

## Nominal Analysis
Most transaction types can be imported with nominal analysis lines, see detailed descriptions below for nominal analysis support.  You can optionally include NominalCode, CostCentre and Department nodes in the import, which are used together to build the Nominal Specification to use for the transaction.   If you have provided any of the nominal fields in the XML the nominal specification must exist in Sage for the transactions to be imported.  If the nominal specification the transaction will not be imported.  If no nominal fields are provided the project nominal or the default nominal for the trader will be used.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
    </Transaction>
  </Transactions>
</Company>
```

## Project Analysis
Most transaction types can be imported with project analysis lines, see detailed descriptions below for project analysis support.  You can optionally include ProjectRef and ProjectItem nodes in the import, which are used together to add the project line to the transactions.  

The project and project item must exist in Sage if the nodes are provided.  Note the nominal information from the project / project item will always be used, even if these are specified in the XML.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <ProjectRef>0000000003</ProjectRef>
      <ProjectItem>DEV</ProjectItem>
    </Transaction>
  </Transactions>
</Company>
```

## Allocations
Most transactions can be allocated during the import, see detailed descriptions below for project analysis support.  There are two separate methods for allocations:

 * Optionally include PaymentReference node
 * Use Auto Allocation setting at the task level

Using the PaymentRef node you can specify the Sage reference of the transaction you want to allocate to.  If the reference cannot be found or is already allocated the transaction will be imported, but left unallocated.  Using the Auto Allocation setting will use the Sage routine to allocate the outstanding amount for all debit transactions, and all credit transactions up to the debit total.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <PaymentReference>SI1</PaymentReference>
    </Transaction>
  </Transactions>
</Company>
```

## Grouping
Most transactions can be grouped during the import, to end with a single transaction in Sage with multiple analysis / project lines.  With the exception of JournalDebits and JournalCredits all transactions are grouped based on a match of TransactionType, AccountReference, TransactionDate, Reference and SecondReference.  JournalDebits and JournalCredits use the same matching except TransactionType, as the two types are used together to create a single journal.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>1</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>ANDREW</AccountReference>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate>
      <Reference>SI1</Reference>
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode>
    </Transaction>
    <Transaction>
      <Id>2</Id>
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>ANDREW</AccountReference>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate>
      <Reference>SI1</Reference>
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode>
    </Transaction>
  </Transactions>
</Company>
```

## Sales Invoice
Supports nominal analysis, project analysis, allocations and grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>1</Id> 
      <TransactionType>SalesInvoice</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>  
      <Reference>SI1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Sales Invoice</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC1</AnalysisCode>
      <VatInclusive>true</VatInclusive>
    </Transaction>
    <Transaction>
      <Id>2</Id> 
      <TransactionType>SalesInvoice</TransactionType>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>SI1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Sales Invoice</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC1</AnalysisCode>
      <VatInclusive>true</VatInclusive>
    </Transaction>  
  </Transactions>
</Company>
```

## Sales Credit
Supports nominal analysis, project analysis, allocations and grouping. 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>3</Id> 
      <TransactionType>SalesCredit</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>SC1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Sales Credit</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC2</AnalysisCode>
    </Transaction>
    <Transaction>
      <Id>4</Id> 
      <TransactionType>SalesCredit</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>SC1</Reference> 
      <PaymentReference></PaymentReference> 
      <Details>Sales Credit</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC2</AnalysisCode>
    </Transaction>  
  </Transactions>
</Company>
```

## Sales Receipt
Supports allocations.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>5</Id> 
      <TransactionType>SalesReceipt</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <PostedDate>2011-01-01T11:11:11</PostedDate> 
      <Reference>SR1</Reference> 
      <SecondReference></SecondReference> 
      <PaymentReference>SI1</PaymentReference> 
      <Details>Sales Receipt</Details> 
      <NetAmount>240</NetAmount>
      <DiscountValue>0</DiscountValue> 
      <BankReference>1000</BankReference> 
    </Transaction>  
  </Transactions>
</Company>
```

## Sales Payment
Supports allocations.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>6</Id> 
      <TransactionType>SalesPayment</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <PostedDate>2011-01-01T11:11:11</PostedDate> 
      <Reference>SP1</Reference> 
      <SecondReference></SecondReference> 
      <PaymentReference>SC1</PaymentReference> 
      <Details>Sales Payment</Details> 
      <NetAmount>240</NetAmount>
      <DiscountValue>0</DiscountValue> 
      <BankReference>1000</BankReference> 
    </Transaction>  
  </Transactions>
</Company>
```

## Purchase Invoice
Supports nominal analysis, project analysis, allocations and grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>7</Id> 
      <TransactionType>PurchaseInvoice</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>SI1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Purchase Invoice</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC3</AnalysisCode>
    </Transaction>
    <Transaction>
      <Id>8</Id> 
      <TransactionType>PurchaseInvoice</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>SI1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Purchase Invoice</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC3</AnalysisCode>
    </Transaction>  
  </Transactions>
</Company>
```

## Purchase Credit
Supports nominal analysis, project analysis, allocations and grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>9</Id> 
      <TransactionType>PurchaseCredit</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>SC1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Purchase Credit</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC4</AnalysisCode>
    </Transaction>
    <Transaction>
      <Id>10</Id> 
      <TransactionType>PurchaseCredit</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>SC1</Reference> 
      <PaymentReference></PaymentReference> 
      <Details>Purchase Credit</Details> 
      <NetAmount>100</NetAmount>
      <TaxAmount>20</TaxAmount>
      <TaxCode>1</TaxCode> 
      <TaxRate>20</TaxRate> 
      <AnalysisCode>AC4</AnalysisCode>
    </Transaction>  
  </Transactions>
</Company>
```

## Purchase Receipt
Supports allocations.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>11</Id> 
      <TransactionType>PurchaseReceipt</TransactionType>
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <PostedDate>2011-01-01T11:11:11</PostedDate> 
      <Reference>SR1</Reference> 
      <SecondReference></SecondReference> 
      <PaymentReference>PI1</PaymentReference> 
      <Details>Purchase Receipt</Details> 
      <NetAmount>240</NetAmount>
      <DiscountValue>0</DiscountValue> 
      <BankReference>1000</BankReference> 
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
      <CustomerId>1</CustomerId>
      <AccountReference>ANDREW</AccountReference> 
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <PostedDate>2011-01-01T11:11:11</PostedDate> 
      <Reference>SP1</Reference> 
      <SecondReference></SecondReference> 
      <PaymentReference>PC1</PaymentReference> 
      <Details>Purchase Payment</Details> 
      <NetAmount>240</NetAmount>
      <DiscountValue>0</DiscountValue> 
      <BankReference>1000</BankReference> 
    </Transaction>  
  </Transactions>
</Company>
```

## Bank Receipt
Supports grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>13</Id> 
      <TransactionType>BankReceipt</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>BR1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Bank Receipt</Details> 
      <NetAmount>100</NetAmount>
      <BankReference>1000</BankReference> 
    </Transaction>
    <Transaction>
      <Id>14</Id> 
      <TransactionType>BankReceipt</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>BR1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Bank Receipt</Details> 
      <NetAmount>100</NetAmount>
      <BankReference>1000</BankReference> 
    </Transaction>  
  </Transactions>
</Company>
```

## Bank Payment
Supports grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>15</Id> 
      <TransactionType>BankPayment</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>BP1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Bank Payment</Details> 
      <NetAmount>100</NetAmount>
      <BankReference>1000</BankReference> 
    </Transaction>
    <Transaction>
      <Id>16</Id> 
      <TransactionType>BankPayment</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>BP1</Reference> 
      <SecondReference></SecondReference> 
      <Details>Bank Payment</Details> 
      <NetAmount>100</NetAmount>
      <BankReference>1000</BankReference> 
    </Transaction>  
  </Transactions>
</Company>
```

## Non-taxable Bank Receipt
Supports grouping. Only supported in Zynk version 2.5 and above.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>15</Id> 
      <TransactionType>BankNonTaxableReceipt</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>BR1</Reference> 
      <SecondReference>A53135</SecondReference> 
      <Details>Bank Receipt</Details> 
      <NetAmount>100</NetAmount>
      <BankReference>1000</BankReference> 
    </Transaction>
  </Transactions>
</Company>
```

## Non-taxable Bank Payment
Supports grouping. Only supported in Zynk version 2.5 and above.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>15</Id> 
      <TransactionType>BankNonTaxablePayment</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>BP1</Reference> 
      <SecondReference>A53135</SecondReference> 
      <Details>Bank Payment</Details> 
      <NetAmount>100</NetAmount>
      <BankReference>1000</BankReference> 
    </Transaction>
  </Transactions>
</Company>
```

## Journal Debit / Credit
Supports nominal analysis, project analysis and grouping.  Note all values must be positive.  Journal Debits / Credits must always be imported together as a group, as they are used together to create a single journal.  The value of the Journal Debit must be equal to the total of the Journal Credits, otherwise the group will fail to import into Sage.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>17</Id> 
      <TransactionType>JournalDebit</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4000</NominalCode>
      <CostCentre>01</CostCentre>
      <Department>01</Department>
      <Reference>NJ1</Reference>
      <Details>Debit</Details> 
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
      <AnalysisCode>AC5</AnalysisCode>
    </Transaction>
    <Transaction>
      <Id>18</Id> 
      <TransactionType>JournalCredit</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4001</NominalCode>
      <CostCentre></CostCentre>
      <Department></Department>
      <Reference>NJ1</Reference>
      <Details>Credit</Details> 
      <NetAmount>50</NetAmount>
      <TaxCode>1</TaxCode>
      <AnalysisCode>AC5</AnalysisCode>
    </Transaction>
    <Transaction>
      <Id>19</Id> 
      <TransactionType>JournalCredit</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <NominalCode>4002</NominalCode>
      <CostCentre></CostCentre>
      <Department></Department>
      <Reference>NJ1</Reference>
      <Details>Credit</Details> 
      <NetAmount>50</NetAmount>
      <TaxCode>1</TaxCode>
      <AnalysisCode>AC5</AnalysisCode>
    </Transaction>  
  </Transactions>
</Company>
```

## Project Cost Opening Balance
Supports project analysis and grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>20</Id> 
      <TransactionType>ProjectCostOpeningBalance</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>PC1</Reference>
      <Details>Opening Cost</Details> 
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>
    <Transaction>
      <Id>21</Id> 
      <TransactionType>ProjectCostOpeningBalance</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>PC1</Reference>
      <Details>Opening Cost</Details> 
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>  
  </Transactions>
</Company>
```

## Project Revenue Opening Balance
Supports project analysis and grouping.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>22</Id> 
      <TransactionType>ProjectRevenueOpeningBalance</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>PR1</Reference>
      <Details>Opening Revenue</Details> 
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>
    <Transaction>
      <Id>23</Id> 
      <TransactionType>ProjectRevenueOpeningBalance</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000003</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>PR1</Reference>
      <Details>Opening Revenue</Details> 
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>  
  </Transactions>
</Company>
```

## Project Cost Adjustment
Supports project analysis and grouping.  Note there must be at least two transactions in the group for the transaction to be imported, and the positive and negative values must equal 0.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>24</Id> 
      <TransactionType>ProjectCostAdjustment</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000004</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>CA1</Reference>
      <Details>Cost Adjustment 1</Details> 
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>
    <Transaction>
      <Id>25</Id> 
      <TransactionType>ProjectCostAdjustment</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000005</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>CA1</Reference>
      <Details>Cost Adjustment 2</Details> 
      <NetAmount>-100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>  
  </Transactions>
</Company>
```

## Project Revenue Adjustment
Supports project analysis and grouping.  Note there must be at least two transactions in the group for the transaction to be imported, and the positive and negative values must equal 0.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Transactions>
    <Transaction>
      <Id>26</Id> 
      <TransactionType>ProjectRevenueAdjustment</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000004</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>RA1</Reference>
      <Details>Revenue Adjustment 1</Details> 
      <NetAmount>100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>
    <Transaction>
      <Id>27</Id> 
      <TransactionType>ProjectRevenueAdjustment</TransactionType>
      <TransactionDate>2011-01-01T11:11:11</TransactionDate> 
      <ProjectRef>0000000005</ProjectRef> 
      <ProjectItem>DEV</ProjectItem> 
      <Reference>RA1</Reference>
      <Details>Revenue Adjustment 2</Details> 
      <NetAmount>-100</NetAmount>
      <TaxCode>1</TaxCode>
    </Transaction>  
  </Transactions>
</Company>
```
