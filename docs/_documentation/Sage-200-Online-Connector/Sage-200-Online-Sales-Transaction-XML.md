---
slug: sage-200-online-sales-transaction-xml
title: Sage 200 Online Sales Transaction XML
---

Sales posted transactions are created when transactions, such as orders invoiced, receipts, refunds or credit notes, are posted against the sales ledger.  Further information can be found on the [Sage 200 Online Sales Posted Transactions API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200extra/accounts/v1/sales_posted_transactions).

## Tasks
 * [Exporting Sales Transactions from Sage 200 Online](exporting-sales-transactions-from-sage-200-online)
 * [Importing Sales Receipts to Sage 200 Online](importing-sales-receipts-to-sage-200-online)

## Fields for Download Only
### id
 _Read Only_  
Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27107 | `<id>27107</id>` |

### customer_id
 _Read Only_  
Customer Id, will also return [customer](#customer) data.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27006 | `<customer_id>27006</customer_id>` |

### trader_transaction_type
 _Read Only_  
Transaction type.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | TradingAccountEntryTypePurchasePaymentSalesReceipt | `<trader_transaction_type>TradingAccountEntryTypePurchasePaymentSalesReceipt</trader_transaction_type>` |

#### Available Values
 * TradingAccountEntryTypeDeletedRecord - Deleted
 * TradingAccountEntryTypePurchasePaymentSalesReceipt - Purchase Payment / Sales Receipt
 * TradingAccountEntryTypePurchaseReceiptSalesPayment - Purchase Receipt / Sales Payment
 * TradingAccountEntryTypeNOTUSED - Unknown
 * TradingAccountEntryTypeInvoice - Invoice
 * TradingAccountEntryTypeCreditNote - Credit Note
 * TradingAccountEntryTypeOpeningBalanceInvoice - Opening Bal. Invoice
 * TradingAccountEntryTypeOpeningBalanceCreditNote - Opening Bal. Credit Note

### reference
 _Read Only_  
Transaction reference.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | Web Sales | `<reference>Web Sales</reference>` |

### second_reference
 _Read Only_  
Second reference.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | Order #12345 | `<second_reference>Order #12345</second_reference>` |

### queried
 _Read Only_  
Query flag.

| Type | Example | XML |
| --- | --- | --- |
| string(1) |  | `<queried />` |

### transaction_date
 _Read Only_  
Transaction date.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-01T00:00:00 | `<transaction_date>2017-06-01T00:00:00</transaction_date>` |

### posted_date
 _Read Only_  
Posted date.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-02T00:00:00 | `<posted_date>2017-06-02T00:00:00</posted_date>` |

### due_date
 _Read Only_  
Due date.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-01T00:00:00 | `<due_date>2017-06-01T00:00:00</due_date>` |

### document_goods_value
 _Read Only_  
Value of the goods.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | -120.00 | `<document_goods_value>-120.00</document_goods_value>` |

### document_gross_value
 _Read Only_  
Gross value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | -120.00 | `<document_gross_value>-120.00</document_gross_value>` |

### document_tax_value
 _Read Only_  
Tax value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.00 | `<document_tax_value>0.00</document_tax_value>` |

### document_discount_value
 _Read Only_  
Document discount value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.00 | `<document_discount_value>0.00</document_discount_value>` |

### discount_percent
 _Read Only_  
Percentage discount.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.00 | `discount_percent>0.00</discount_percent>` |

### document_tax_discount_value
 _Read Only_  
Tax discount value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.00 | `<document_tax_discount_value>0.00</document_tax_discount_value>` |

### document_allocated_value
 _Read Only_  
Allocated value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.00 | `<document_allocated_value>0.00</document_allocated_value>` |

### document_outstanding_value
 _Read Only_  
Outstanding value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | -120.00 | `<document_outstanding_value>-120.00</document_outstanding_value>` |

### base_goods_value
 _Read Only_  
Value of the goods in base currency.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | -120.0< | `<base_goods_value>-120.0</base_goods_value>` |

### base_gross_value
 _Read Only_  
Gross value in base currency.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | -120.0 | `<base_gross_value>-120.0</base_gross_value>` |

### base_tax_value
 _Read Only_  
Tax value in base currency.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.0 | `<base_tax_value>0.0</base_tax_value>` |

### base_discount_value
 _Read Only_  
Discount value in base currency.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.0 | `<base_discount_value>0.0</base_discount_value>` |

### base_tax_discount_value
 _Read Only_  
Tax discount value in base currency.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.0 | `<base_tax_discount_value>0.0</base_tax_discount_value>` |

### base_allocated_value
 _Read Only_  
Allocated value in base currency.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.0 | `<base_allocated_value>0.0</base_allocated_value>` |

### control_value_in_base_currency
 _Read Only_  
Control value in base currency.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | -120.00 | `<control_value_in_base_currency>-120.00</control_value_in_base_currency>` |

### exchange_rate
 _Read Only_  
Exchange rate used for transaction.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 6dp) | 1.000000 | `<exchange_rate>1.000000</exchange_rate>` |

### settled_immediately
 _Read Only_  
Immediately settled.

| Type | Example | XML |
| --- | --- | --- |
| boolean | false | `<settled_immediately>false</settled_immediately>` |

#### Available Values
 * true
 * false

### discount_days
 _Read Only_  
Number of days discount valid.

| Type | Example | XML |
| --- | --- | --- |
| integer(int16) | 0 | `<discount_days>0</discount_days>` |

### urn
 _Read Only_  
Unique reference number.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 31 | `<urn>31</urn>` |

### user_name
 _Read Only_  
User who entered the transaction.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | Demo Site | `<user_name>Demo Site</user_name>` |

### date_time_updated
 _Read Only_  
The date and time this entity was last updated (UTC).

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-02T15:08:33.673 | `<date_time_updated>2017-06-02T15:08:33.673</date_time_updated>` |

### tax_analysis_items
 _Read Only_  
A collection of tax analysis items, see full example XML below.

#### id
_Read Only_  
Tax code Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 2 | `<id>2</id` |

#### goods_amount
_Read Only_  
Goods amount.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 20.00 | `<goods_amount>20.00</goods_amount>` |

#### tax_amount
_Read Only_  
Tax amount.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 4.00 | `<tax_amount>4.00</tax_amount>` |

### nominal_analysis_items
 _Read Only_  
A collection of nominal analysis items, see full example XML below.

#### code
_Read Only_  
Nominal account code.

| Type | Example | XML |
| --- | --- | --- |
| string(8) | 1200 | `<code>1200</code>` |

#### cost_centre
_Read Only_  
Cost centre.

| Type | Example | XML |
| --- | --- | --- |
| string(3) |  | `<cost_centre />` |

#### department
_Read Only_  
Department.

| Type | Example | XML |
| --- | --- | --- |
| string(3) |  | `<department />` |

#### narrative
_Read Only_  
Narrative.

| Type | Example | XML |
| --- | --- | --- |
| string(6000) | SR /  ZYNK001 | `<narrative>SR /  ZYNK001</narrative>` |

#### value
_Read Only_  
Goods value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 120.00 | `<value>120.00</value>` |

### bank_items
 _Read Only_  
A collection of bank items, see full example XML below.

#### bank_code
_Read Only_  
Bank account code.

| Type | Example | XML |
| --- | --- | --- |
| string() | DEFAULT | `<bank_code>DEFAULT</bank_code>` |

#### name
_Read Only_  
Account name.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Default | `<name>Default</name>` |

#### bank_entry_type
_Read Only_  
Bank entry type.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | Receipt | `<bank_entry_type>Receipt</bank_entry_type>` |

#### reference
_Read Only_  
Reference.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | Web Sales | `<reference>Web Sales</reference>` |

#### cheque_value
_Read Only_  
Value of item.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) |  | `<cheque_value>120.00</cheque_value>` |

#### 
_Read Only_  


| Type | Example | XML |
| --- | --- | --- |
|  |  | `` |

### allocation_session_items
 _Read Only_  
A collection of allocation session items, see full example XML below.

#### user_name
_Read Only_  
Name of user that entered item.

| Type | Example | XML |
| --- | --- | --- |
| string() | Demo Site | `<user_name>Demo Site</user_name>` |

#### ledger_type
_Read Only_  
Ledger type. 

| Type | Example | XML |
| --- | --- | --- |
| string(30) | LedgerSales | `<ledger_type>LedgerSales</ledger_type>` |

#### Available Values
 * LedgerNotSpecified - Not Specified
 * LedgerSales - Sales
 * LedgerPurchase - Purchase
 * LedgerNominal - Nominal
 * LedgerPayroll - Payroll
 * LedgerProjectCosting - Project Accounting
 * LedgerStockControl - Stock Control
 * LedgerSOP - SOP
 * LedgerPOP - POP
 * LedgerInvoicing - Invoicing
 * LedgerCashBook - Cash Book
 * LedgerBOM - BOM
 * LedgerFixedAssets - Fixed Assets
 * LedgerRetail - Retail
 * LedgerManufacturing - Manufacturing
 * LedgerWebAPI - Web API
 * LedgerBankFeeds - Bank Feeds
 * LedgerEducation - Education
 * LedgerExcelReporting - Excel Reporting
 * LedgerBI - Business Intelligence
 * LedgerPriceBook - Price Book
 * LedgerTax - Tax
 * LedgerUnknownSource - Unknown

#### urn
_Read Only_  
Unique reference number.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 4 | <urn>4</urn>` |

#### allocation_date
_Read Only_  
Date of allocation.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2016-07-07T00:00:00 | `<allocation_date>2016-07-07T00:00:00</allocation_date>` |

#### trader_transaction_type
_Read Only_  
Transaction type.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | TradingAccountEntryTypeInvoice | `<trader_transaction_type>TradingAccountEntryTypeInvoice</trader_transaction_type>` |

#### Available Values
 * TradingAccountEntryTypeDeletedRecord - Deleted
 * TradingAccountEntryTypePurchasePaymentSalesReceipt - Purchase Payment / Sales Receipt
 * TradingAccountEntryTypePurchaseReceiptSalesPayment - Purchase Receipt / Sales Payment
 * TradingAccountEntryTypeNOTUSED - Unknown
 * TradingAccountEntryTypeInvoice - Invoice
 * TradingAccountEntryTypeCreditNote - Credit Note
 * TradingAccountEntryTypeOpeningBalanceInvoice - Opening Bal. Invoice
 * TradingAccountEntryTypeOpeningBalanceCreditNote - Opening Bal. Credit Note

#### reference
_Read Only_  
Reference.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | 0000000123 | `<reference>0000000123</reference>` |

#### value
_Read Only_  
Value of allocation item.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 12.00 | `<value>12.00</value>` |

#### allocation_value
_Read Only_  
Value of allocation.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 12.00 | `<allocation_value>12.00</allocation_value>` |

### allocation_history_items
 _Read Only_  
A collection of allocation history items, see full example XML below.

#### allocation_value
_Read Only_  
Value of allocation.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 12.00 | `<allocation_value>12.00</allocation_value>` |

## Expandable Fields
Related information linked to sales transactions are also included in the exported XML.

### Customer
_Dependant (see [customer_id](#customer_id))_  
On a download all the related information of the customer will be included in the XML, see [Sage 200 Online Customer XML](sage-200-online-customer-xml).

#### Export example showing related information

```xml
<customer>
    <id>27006</id>
    <date_time_updated>2017-06-05T15:24:29.723</date_time_updated>
    <reference>ZYNK001</reference>
    <name>Zynk Software Ltd.</name>
    <short_name>Zynk</short_name>
    <balance>-480.00</balance>
    <on_hold>false</on_hold>
    <account_status_type>AccountStatusActive</account_status_type>
    <currency_id>1</currency_id>
    <exchange_rate_type>ExchangeRateSingle</exchange_rate_type>
    <telephone_country_code>+44</telephone_country_code>
    <telephone_area_code>191</telephone_area_code>
    <telephone_subscriber_number>303 7279</telephone_subscriber_number>
    <fax_country_code>+44</fax_country_code>
    <fax_area_code>845</fax_area_code>
    <fax_subscriber_number>123 2920</fax_subscriber_number>
    <website>http://zynk.com</website>
    <credit_limit>10000.00</credit_limit>
    <country_code_id>13</country_code_id>
    <default_tax_code_id>2</default_tax_code_id>
    <vat_number>796 5763 59</vat_number>
    <analysis_code_1>North</analysis_code_1>
    <analysis_code_2>Software</analysis_code_2>
    <analysis_code_3>01/01/2005</analysis_code_3>
    <analysis_code_4>10</analysis_code_4>
    <analysis_code_5>true</analysis_code_5>
    <duns_code>424458615</duns_code>
</customer>
```

## Example XML
### Sales Receipt

```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesTransactions xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesTransaction>
    <id>27107</id>
    <date_time_updated>2017-06-02T15:08:33.673</date_time_updated>
    <trader_transaction_type>TradingAccountEntryTypePurchasePaymentSalesReceipt</trader_transaction_type>
    <reference>Web Sales</reference>
    <second_reference>Order #12345</second_reference>
    <queried />
    <transaction_date>2017-06-01T00:00:00</transaction_date>
    <posted_date>2017-06-02T00:00:00</posted_date>
    <due_date>2017-06-01T00:00:00</due_date>
    <document_goods_value>-120.00</document_goods_value>
    <document_gross_value>-120.00</document_gross_value>
    <document_tax_value>0.00</document_tax_value>
    <document_discount_value>0.00</document_discount_value>
    <discount_percent>0.00</discount_percent>
    <document_tax_discount_value>0.00</document_tax_discount_value>
    <document_allocated_value>0.00</document_allocated_value>
    <document_outstanding_value>-120.00</document_outstanding_value>
    <base_goods_value>-120.0</base_goods_value>
    <base_gross_value>-120.0</base_gross_value>
    <base_tax_value>0.0</base_tax_value>
    <base_discount_value>0.0</base_discount_value>
    <base_tax_discount_value>0.0</base_tax_discount_value>
    <base_allocated_value>0.0</base_allocated_value>
    <control_value_in_base_currency>-120.00</control_value_in_base_currency>
    <exchange_rate>1.000000</exchange_rate>
    <settled_immediately>false</settled_immediately>
    <discount_days>0</discount_days>
    <urn>31</urn>
    <user_name>Demo Site</user_name>
    <tax_analysis_items />
    <nominal_analysis_items>
      <nominal_analysis_item>
        <code>1100</code>
        <cost_centre />
        <department />
        <narrative>SR /  ZYNK001</narrative>
        <value>-120.00</value>
      </nominal_analysis_item>
      <nominal_analysis_item>
        <code>1200</code>
        <cost_centre />
        <department />
        <narrative>SR /  ZYNK001</narrative>
        <value>120.00</value>
      </nominal_analysis_item>
    </nominal_analysis_items>
    <bank_items>
      <bank_item>
        <bank_code>DEFAULT</bank_code>
        <name>Default</name>
        <bank_entry_type>Receipt</bank_entry_type>
        <reference>Web Sales</reference>
        <cheque_value>120.00</cheque_value>
        <statement_date xsi:nil="true" />
        <statement_page_number xsi:nil="true" />
        <urn>31</urn>
      </bank_item>
    </bank_items>
    <allocation_session_items />
    <allocation_history_items />
    <customer_id>27006</customer_id>
    <customer>
      <id>27006</id>
      <date_time_updated>2017-06-06T11:45:50.363</date_time_updated>
      <reference>ZYNK001</reference>
      <name>Zynk Software Ltd.</name>
      <short_name>Zynk</short_name>
      <balance>-480.00</balance>
      <on_hold>false</on_hold>
      <account_status_type>AccountStatusActive</account_status_type>
      <currency_id>1</currency_id>
      <exchange_rate_type>ExchangeRateSingle</exchange_rate_type>
      <telephone_country_code>+44</telephone_country_code>
      <telephone_area_code>191</telephone_area_code>
      <telephone_subscriber_number>303 7279</telephone_subscriber_number>
      <fax_country_code>+44</fax_country_code>
      <fax_area_code>845</fax_area_code>
      <fax_subscriber_number>123 2920</fax_subscriber_number>
      <website>http://zynk.com</website>
      <credit_limit>10000.00</credit_limit>
      <country_code_id>13</country_code_id>
      <default_tax_code_id>2</default_tax_code_id>
      <vat_number>796 5763 59</vat_number>
      <analysis_code_1>North</analysis_code_1>
      <analysis_code_2>Software</analysis_code_2>
      <analysis_code_3>01/01/2005</analysis_code_3>
      <analysis_code_4>10</analysis_code_4>
      <analysis_code_5>true</analysis_code_5>
      <duns_code>424458615</duns_code>
    </customer>
  </SalesTransaction>
</SalesTransactions>
```

### Sales Invoice

```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesTransactions xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesTransaction>
    <id>18406</id>
    <date_time_updated>2016-07-07T14:27:49.053</date_time_updated>
    <trader_transaction_type>TradingAccountEntryTypeInvoice</trader_transaction_type>
    <reference>0000000123</reference>
    <second_reference>0000000123</second_reference>
    <queried />
    <transaction_date>2016-05-22T00:00:00</transaction_date>
    <posted_date>2016-05-23T00:00:00</posted_date>
    <due_date>2016-06-07T00:00:00</due_date>
    <document_goods_value>10.00</document_goods_value>
    <document_gross_value>12.00</document_gross_value>
    <document_tax_value>2.00</document_tax_value>
    <document_discount_value>0.00</document_discount_value>
    <discount_percent>0.00</discount_percent>
    <document_tax_discount_value>0.00</document_tax_discount_value>
    <document_allocated_value>12.00</document_allocated_value>
    <document_outstanding_value>0.00</document_outstanding_value>
    <base_goods_value>10.0</base_goods_value>
    <base_gross_value>12.0</base_gross_value>
    <base_tax_value>2.0</base_tax_value>
    <base_discount_value>0.0</base_discount_value>
    <base_tax_discount_value>0.0</base_tax_discount_value>
    <base_allocated_value>12.0</base_allocated_value>
    <control_value_in_base_currency>0.00</control_value_in_base_currency>
    <exchange_rate>1.000000</exchange_rate>
    <settled_immediately>false</settled_immediately>
    <discount_days>0</discount_days>
    <urn>4</urn>
    <user_name>Demo Site</user_name>
    <tax_analysis_items>
      <tax_analysis_item>
        <id>2</id>
        <goods_amount>10.00</goods_amount>
        <discount_amount xsi:nil="true" />
        <tax_amount>2.00</tax_amount>
        <goods_discount_amount xsi:nil="true" />
      </tax_analysis_item>
    </tax_analysis_items>
    <nominal_analysis_items>
      <nominal_analysis_item>
        <code />
        <cost_centre />
        <department />
        <narrative>SI / ZYNK0001</narrative>
        <value>-10.00</value>
      </nominal_analysis_item>
      <nominal_analysis_item>
        <code />
        <cost_centre />
        <department />
        <narrative>SI / ZYNK0001</narrative>
        <value>-2.00</value>
      </nominal_analysis_item>
      <nominal_analysis_item>
        <code />
        <cost_centre />
        <department />
        <narrative>SI / ZYNK0001</narrative>
        <value>12.00</value>
      </nominal_analysis_item>
    </nominal_analysis_items>
    <bank_items />
    <allocation_session_items>
      <allocation_session_item>
        <user_name>Demo Site</user_name>
        <ledger_type>LedgerSales</ledger_type>
        <urn>12</urn>
        <allocation_date>2016-07-07T00:00:00</allocation_date>
        <trader_transaction_type>TradingAccountEntryTypePurchasePaymentSalesReceipt</trader_transaction_type>
        <reference>reciept</reference>
        <value>-20.00</value>
        <allocation_value>-20.00</allocation_value>
      </allocation_session_item>
      <allocation_session_item>
        <user_name>Demo Site</user_name>
        <ledger_type>LedgerSales</ledger_type>
        <urn>4</urn>
        <allocation_date>2016-07-07T00:00:00</allocation_date>
        <trader_transaction_type>TradingAccountEntryTypeInvoice</trader_transaction_type>
        <reference>0000000123</reference>
        <value>12.00</value>
        <allocation_value>12.00</allocation_value>
      </allocation_session_item>
      <allocation_session_item>
        <user_name>Demo Site</user_name>
        <ledger_type>LedgerSales</ledger_type>
        <urn>5</urn>
        <allocation_date>2016-07-07T00:00:00</allocation_date>
        <trader_transaction_type>TradingAccountEntryTypeInvoice</trader_transaction_type>
        <reference>0000000123</reference>
        <value>12.00</value>
        <allocation_value>8.00</allocation_value>
      </allocation_session_item>
    </allocation_session_items>
    <allocation_history_items>
      <allocation_history_item>
        <urn xsi:nil="true" />
        <allocation_date xsi:nil="true" />
        <value xsi:nil="true" />
        <allocation_value>12.00</allocation_value>
      </allocation_history_item>
    </allocation_history_items>
    <customer_id>14950</customer_id>
    <customer>
      <id>14950</id>
      <date_time_updated>2017-01-25T11:05:10.687</date_time_updated>
      <reference>ZYNK0001</reference>
      <name>Zynk Software</name>
      <short_name>Zynk Sof</short_name>
      <balance>-1929.60</balance>
      <on_hold>false</on_hold>
      <account_status_type>AccountStatusActive</account_status_type>
      <currency_id>1</currency_id>
      <exchange_rate_type>ExchangeRateSingle</exchange_rate_type>
      <telephone_country_code>00</telephone_country_code>
      <telephone_area_code>11</telephone_area_code>
      <telephone_subscriber_number>22</telephone_subscriber_number>
      <fax_country_code>33</fax_country_code>
      <fax_area_code>44</fax_area_code>
      <fax_subscriber_number>55</fax_subscriber_number>
      <website>web</website>
      <credit_limit>10000.00</credit_limit>
      <country_code_id>100224</country_code_id>
      <default_tax_code_id>2</default_tax_code_id>
      <vat_number>vat num</vat_number>
      <analysis_code_1>analysis 1</analysis_code_1>
      <analysis_code_2>analysis 2</analysis_code_2>
      <analysis_code_3>analysis 3</analysis_code_3>
      <analysis_code_4>analysis 4</analysis_code_4>
      <analysis_code_5>analysis 5</analysis_code_5>
      <duns_code>014785236</duns_code>
    </customer>
  </SalesTransaction>
</SalesTransactions>
```