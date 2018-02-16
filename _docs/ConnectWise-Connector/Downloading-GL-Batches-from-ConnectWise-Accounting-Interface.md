---
slug: downloading-gl-batches-from-connectwise-accounting-interface
redirect_from: "/article/926-downloading-gl-batches-from-connectwise"
title: Downloading GL Batches from ConnectWise Accounting Interface
---


This task will retrieve Unposted Invoices, Unposted Expenses and/or Unposted Procurement data from the Accounting Interface in ConnectWise. This task is typically used for integrations with accounting systems, as the data provided from ConnectWise includes the general ledger account numbers associated with the transactions.


## Settings

### Connection
Required

The ConnectWise Company to Download GL Batch data from. The ConnectWise user's security role must have Add Level access to the Accounting Interface in order to use this task. Click the link if you require more information on how to create/manage this type of connection.

### Output File
Required

An absolute or relative file path on the local computer or network to save any downloaded data to. This will be defaulted to the current working directory\connectwise\_accounting\_interface\_get\_batch.xml.

### Owner Level
Optional

Filter to restrict the records that are returned based on Location (Level 2 of the Corporate Structure). You can specify the Location Description or Id.

### Thru Date
Optional 

Filter to restrict the records that are returned based on the date they were taken.	If no value is specified the default used by ConnectWise is the current date.

### Export Unposted Expenses
Required

Specify whether Unposted Expenses should be included in the data. This will be defaulted to False.

### Export Unposted Invoices
Required

Specify whether Unposted Procurement should be included in the data. This will be defaulted to False.

### Export Unposted Procurement
Required

Specify whether Unposted Procurement should be included in the data. This will be defaulted to False.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


Sample Unposted Expenses data:


```
<?xml version="1.0" encoding="utf-8"?>
    <GLExport CogsOption="True" SalesTaxOption="True" SalesTaxGroupsOption="False" InventoryPostOption="True" ExpenseAsBillOption="True" ExpenseSummaryOption="False" ExportInvoices="False" ExportExpenses="True" ExportInventory="False" SyncPayments="False" GLBatchID="dda3abde-ab43-4242-9d3b-780038e674c4" LastPaymentSync="" DropShipCogsOption="False" UomProductOption="False">
    <Vendors>
    	<Vendor MemberID="Admin1" VendorName="Admin1" CompanyName="" VendorNumber="ZYNK" FirstName="Training" MiddleInitial="" LastName="Admin1" AccountNumber="" SiteName="" AddressLine1="" AddressLine2="" AddressLine3="" City="" State="" PostalCode="" Country="" CountryCode="" PhoneNumber="(813) 111-1111" BillingTerms="" DueDays="" TaxGroup="" />
    </Vendors>
    <Customers>
    	<Customer CompanyName="Administration Resources Corporation" ContactName="Marc Mosiman" SiteName="Main" AddressLine1="11490 Xeon St. NW" AddressLine2="Suite 200" AddressLine3="Coon Rapids, MN TT3 PYT" City="Coon Rapids" State="MN" PostalCode="TT3 PYT" Country="United States" CountryCode="" PhoneNumber="7634215510" Taxable="True" AccountNumber="12345678" BillingTerms="Net 10" BillingTermsXref="Net 10" TaxCode="T1" StateTaxXref="T1" CountyTaxXref="" CityTaxXref="" Level4TaxXref="" Level5TaxXref="" StateTaxRate="20.00%" CountyTaxRate="0.00%" CityTaxRate="0.00%" Level4TaxRate="0.00%" Level5TaxRate="0.00%" TaxAgencyXref="12345678" StateTaxAgencyXref="12345678" CountyTaxAgencyXref="12345678" CityTaxAgencyXref="12345678" Level4TaxAgencyXref="12345678" Level5TaxAgencyXref="12345678" TaxAccountNumber="9999" TaxRate="20.00%" DueDays="10" CurrencyID="EUR" CompanyType="Customer" ContactEmailAddress="marcm@arcadministration.com" />
    </Customers>
    <ExpenseBills NonReimbursableExpenseRecIDs="1132,1133,1134,1135,1136,1137">
    	<ExpenseTransaction Memo="Expenses for 2011-04-09 - 2011-04-15" VendorNumber="ZYNK" MemberID="Admin1" FirstName="Training" LastName="Admin1" DocumentType="GENERAL JOURNAL" DocumentDate="2011-04-15" DocumentNumber="1132Admin1" APAccountNumber="5000" Class="" CurrencyID="FRF" GLEntryRecID="1132" Total="33.95">
    		<ExpenseDetail GLTypeID="EE" Memo="Mileage" AccountNumber="5000" Class="" Total="2.45" CompanyName="Administration Resources Corporation" CompanyAccountNumber="12345678" DocumentDate="2011-04-15" Billable="True" Reimbursable="True" CompanyAdvance="False" CurrencyID="FRF" GLEntryRecID="1138,1139" />
    		<ExpenseDetail GLTypeID="EE" Memo="Mileage" AccountNumber="5000" Class="" Total="31.50" CompanyName="Administration Resources Corporation" CompanyAccountNumber="12345678" DocumentDate="2011-04-15" Billable="False" Reimbursable="True" CompanyAdvance="False" CurrencyID="FRF" GLEntryRecID="1140,1141" />
    	</ExpenseTransaction>
    </ExpenseBills>
    </GLExport>
```

Sample Unposted Invoices data:

```
<?xml version="1.0" encoding="utf-8"?>
    <GLExport CogsOption="True" SalesTaxOption="True" SalesTaxGroupsOption="False" InventoryPostOption="True" ExpenseAsBillOption="True" ExpenseSummaryOption="False" ExportInvoices="True" ExportExpenses="False" ExportInventory="False" SyncPayments="False" GLBatchID="4531905d-2e3e-428c-b5b6-0ea196534ba8" LastPaymentSync="" DropShipCogsOption="False" UomProductOption="False">
    <Customers>
    	<Customer CompanyName="Zynk Software Limited" ContactName="Zynk Support" SiteName="Main" AddressLine1="6 - 8 Charlotte Square" AddressLine2="" AddressLine3="Newcastle Upon Tyne, HI NE1 4XF" City="Newcastle Upon Tyne" State="HI" PostalCode="NE1 4XF" Country="United Kingdom" CountryCode="" PhoneNumber="" Taxable="True" AccountNumber="ZYNK0001" BillingTerms="Net 10" BillingTermsXref="Net 10" TaxCode="T1" StateTaxXref="T1" CountyTaxXref="" CityTaxXref="" Level4TaxXref="" Level5TaxXref="" StateTaxRate="20.00%" CountyTaxRate="0.00%" CityTaxRate="0.00%" Level4TaxRate="0.00%" Level5TaxRate="0.00%" TaxAgencyXref="ZYNK0001" StateTaxAgencyXref="ZYNK0001" CountyTaxAgencyXref="ZYNK0001" CityTaxAgencyXref="ZYNK0001" Level4TaxAgencyXref="ZYNK0001" Level5TaxAgencyXref="ZYNK0001" TaxAccountNumber="9999" TaxRate="20.00%" DueDays="10" CurrencyID="GBP" CompanyType="Customer" ContactEmailAddress="support@zynk.com" />
    </Customers>
    <Transactions>
    	<Transaction DocumentType="INVOICE" DocumentDate="2014-05-07" CompanyName="Zynk Software Limited" ProjectName="" Total="42.00" TaxableTotal="35.00" SalesTax="7.00" StateTax="7.00" CountyTax="0.00" CityTax="0.00" TaxableAmount1="35.00" TaxableAmount2="0.00" TaxableAmount3="0.00" TaxableAmount4="0.00" TaxableAmount5="0.00" DocumentNumber="12331233" Memo="Imported from ConnectWise" Description="Accounts Receivable" Taxable="Y" TaxCode="1" TaxGroup="Standard VAT" TaxGroupRate="20.000000" TaxAccountNumber="9999" PiggyBackFlag="False" Attention="Zynk Support" SiteName="Main" AddressLine1="6 - 8 Charlotte Square" AddressLine2="" AddressLine3="Newcastle Upon Tyne, HI NE1 4XF" City="Newcastle Upon Tyne" State="HI" PostalCode="NE1 4XF" Country="United Kingdom" CountryCode="" PhoneNumber="01913037279" ShipCompanyAccountNumber="ZYNK0001" ShipCompanyType="Customer" ShipTaxID="" ShipCompanyName="Zynk Software Limited" ShipSiteName="Main" ShipAddressLine1="6 - 8 Charlotte Square" ShipAddressLine2="" ShipAddressLine3="Newcastle Upon Tyne, HI NE1 4XF" ShipCity="Newcastle Upon Tyne" ShipState="HI" ShipPostalCode="NE1 4XF" ShipCountry="United Kingdom" ShipCountryCode="" ShipPhoneNumber="01913037279" ShipContactName="Zynk Support" BillingTerms="Net 10" BillingTermsXref="Net 10" DueDays="10" DueDate="2014-05-17" AccountNumber="9999" Class="" GLEntryRecID="1504,1505,1506,1507,1508,1509" CompanyAccountNumber="ZYNK0001" TaxAgencyXref="ZYNK0001" StateTaxXref="T1" CountyTaxXref="" CityTaxXref="" SalesRepID="" SalesRepName="" PONumber="CUSTOMER PO" GLTypeID="AR" SalesTerritory="My Accounts" CurrencyID="FRF" CompanyType="Customer" BillingType="Miscellaneous" TaxDPAppliedFlag="N" EmailDeliveryFlag="N" PrintDeliveryFlag="N" AgreementPrePaymentFlag="N" TaxID="" UseAvalara="N" SendAvalaraTax="N">
    		<Detail DocumentType="INVOICE" DocumentDate="2014-05-07" AccountNumber="4001:" Class="" Cost="1.25" CostAccountNumber="1111" InventoryAccountNumber="1111" ProductAccountNumber="4001:" SalesCode="1111" Taxable="Y" Taxable2="N" Taxable3="N" Taxable4="N" Taxable5="N" ItemTaxable="Y" ItemID="PATCH10" ItemPrice="7.00" ItemCost="0.25" Memo="10ft Patch Cat5E Cable" Description="Taxable Products" GLEntryRecID="1503" GLTypeID="RP" GLItemID="PATCH10" ItemTypeXref="" InventoryXref="1111" CogsXref="1111" SalesDescription="10ft Patch Cat5E Cable" ItemDescription="10ft Patch Cable" CurrencyID="FRF" UomName="Each" PriceLevelXref="DEFAULT" LocationXref="DEFAULT" BinDescription="Default" WarehouseSiteName="" WarehouseAddressLine1="" WarehouseAddressLine2="" WarehouseCity="" WarehouseState="" WarehouseZip="" WarehouseCountry="" WarehouseCountryCode="" UomScheduleXref="" SubCatDescription="Miscellaneous" Serialized="N" SerialNumbers="" Dropshipped="Y" ShipmentMethod="" TaxCodeXref="T1" InvoiceSummaryOption="0" TimeEntryRecId="" Total="-35.00" Quantity="-5.00" TaxRate="" TaxCode="" TaxAgencyXref="" TaxNote="" />
    		<Detail DocumentType="INVOICE" DocumentDate="2014-05-07" AccountNumber="9999" Class="" Cost="0.00" CostAccountNumber="" InventoryAccountNumber="" ProductAccountNumber="4000" SalesCode="" Taxable="N" Taxable2="N" Taxable3="N" Taxable4="N" Taxable5="N" ItemTaxable="N" ItemID="" ItemPrice="0" ItemCost="0" Memo="Sales Tax" Description="Level 1 Sales Tax" GLEntryRecID="1510" GLTypeID="ST" GLItemID="" ItemTypeXref="" InventoryXref="" CogsXref="" SalesDescription="" ItemDescription="" CurrencyID="FRF" UomName="Hour" PriceLevelXref="DEFAULT" LocationXref="DEFAULT" BinDescription="DEFAULT" WarehouseSiteName="" WarehouseAddressLine1="" WarehouseAddressLine2="" WarehouseCity="" WarehouseState="" WarehouseZip="" WarehouseCountry="" WarehouseCountryCode="" UomScheduleXref="" SubCatDescription="DEFAULT" Serialized="N" SerialNumbers="" Dropshipped="N" ShipmentMethod="" TaxCodeXref="T9" InvoiceSummaryOption="0" TimeEntryRecId="" Total="-7.00" Quantity="0" TaxRate="0.20%" TaxRatePercent="20.00%" TaxCode="T1" TaxAgencyXref="" TaxNote="AUTOSTAX" />
    	</Transaction>
    </Transactions>
    </GLExport>
```

Sample Unposted Procurement data:


```
<?xml version="1.0" encoding="utf-8"?>
    <GLExport CogsOption="True" SalesTaxOption="True" SalesTaxGroupsOption="False" InventoryPostOption="True" ExpenseAsBillOption="True" ExpenseSummaryOption="False" ExportInvoices="False" ExportExpenses="False" ExportInventory="True" SyncPayments="False" GLBatchID="ec5dfcd6-1084-477d-b28a-2bcdf1f2b746" LastPaymentSync="" DropShipCogsOption="False" UomProductOption="False">
    <Vendors>
    	<Vendor MemberID="" VendorName="ConnectWise" CompanyName="ConnectWise" VendorNumber="CW0001" FirstName="Arnie" MiddleInitial="" LastName="Bellini" AccountNumber="CW0001" SiteName="Main" AddressLine1="2803 W Busch Blvd" AddressLine2="Suite 204" AddressLine3="Tampa, FL 33618" City="Tampa" State="FL" PostalCode="33618" Country="" CountryCode="" PhoneNumber="8139357100" BillingTerms="Net 10" DueDays="10" TaxGroup="Standard VAT" />
    </Vendors>
    <Customers>
    	<Customer CompanyName="Zynk Software Limited" ContactName="Zynk Support" SiteName="Main" AddressLine1="6 - 8 Charlotte Square" AddressLine2="" AddressLine3="Newcastle Upon Tyne, HI NE1 4XF" City="Newcastle Upon Tyne" State="HI" PostalCode="NE1 4XF" Country="United Kingdom" CountryCode="" PhoneNumber="" Taxable="True" AccountNumber="ZYNK0001" BillingTerms="Net 10" BillingTermsXref="Net 10" TaxCode="T1" StateTaxXref="T1" CountyTaxXref="" CityTaxXref="" Level4TaxXref="" Level5TaxXref="" StateTaxRate="20.00%" CountyTaxRate="0.00%" CityTaxRate="0.00%" Level4TaxRate="0.00%" Level5TaxRate="0.00%" TaxAgencyXref="ZYNK0001" StateTaxAgencyXref="ZYNK0001" CountyTaxAgencyXref="ZYNK0001" CityTaxAgencyXref="ZYNK0001" Level4TaxAgencyXref="ZYNK0001" Level5TaxAgencyXref="ZYNK0001" TaxAccountNumber="9999" TaxRate="20.00%" DueDays="10" CurrencyID="GBP" CompanyType="Customer" ContactEmailAddress="support@zynk.com" />
    </Customers>
    <PurchaseTransactions>
    	<PurchaseTransaction DocumentNumber="COMPANYBPO" DocumentDate="2014-05-01" PurchaseDate="2014-05-01" VendorName="ConnectWise" VendorNumber="CW0001" VendorAccountNumber="CW0001" VendorInvoiceNumber="COMPANYBINV" VendorInvoiceDate="2014-05-01" FreightAmount="" FreightPackingSlip="COMPANYBPO" APAccountNumber="9000" Class="" ContactName="Arnie Bellini" SiteName="Main" AddressLine1="2803 W Busch Blvd" AddressLine2="Suite 204" AddressLine3="Tampa, FL 33618" City="Tampa" State="FL" PostalCode="33618" Country="" CountryCode="" PhoneNumber="8139357100" Description="Purchase" Memo="PO #COMPANYBPO, Packing Slip: COMPANYBPO" BillingTerms="Net 10" CurrencyID="GBP" PackingSlip="COMPANYBPO" BillingTermsXref="Net 10" CompanyType="Vendor" TaxCode="1" TaxGroup="Standard VAT" TaxGroupRate="20.000000" TaxAgencyXref="" StateTaxXref="T1" CountyTaxXref="" CityTaxXref="" ShipToCompanyName="Zynk Software Limited" ShipToCompanyAccountNumber="ZYNK0001" ShipToCompanyType="Customer" ShipToContactName="Zynk Support" ShipToSiteName="Main" ShipToAddressLine1="6 - 8 Charlotte Square" ShipToAddressLine2="" ShipToAddressLine3="Newcastle Upon Tyne, HI NE1 4XF" ShipToCity="Newcastle Upon Tyne" ShipToState="HI" ShipToPostalCode="NE1 4XF" ShipToCountry="United Kingdom" ShipToCountryCode="" ShipToPhoneNumber="" ShipToTaxGroup="Standard VAT" Dropshipped="Y" DueDays="10" UseAvalara="N" PurchaseHeaderTaxGroup="Standard VAT" PurchaseHeaderTaxable="N" PurchaseHeaderFreightTaxable="N" PurchaseInformation="PO #COMPANYBPO, Packing Slip: COMPANYBPO" Total="12.50">
    		<PurchaseDetail DocumentDate="5/1/2014 5:21:58 AM" AccountNumber="4001" Class="" Cost="12.50" CostAccountNumber="1111" InventoryAccountNumber="1111" SalesCode="1111" Taxable="Y" ItemID="PATCH10" Quantity="-50.00" ItemPrice="7.00" ItemCost="0.25" Total="-12.50" Description="Purchase" GLEntryRecID="1299" GLTypeID="RP" GLItemID="PATCH10" ItemTypeXref="" InventoryXref="1111" CogsXref="1111" SalesDescription="10ft Patch Cat5E Cable" ItemDescription="10ft Patch Cable" Memo="10ft Patch Cable" TaxNote="" VendorAccountNumber="CW0001" VendorNumber="CW0001" CurrencyID="GBP" UomName="Each" PriceLevelXref="DEFAULT" LocationXref="DEFAULT" BinDescription="DEFAULT" WarehouseSiteName="" WarehouseAddressLine1="" WarehouseAddressLine2="" WarehouseCity="" WarehouseState="" WarehouseZip="" WarehouseCountry="" WarehouseCountryCode="" UomScheduleXref="DEFAULT" SubCatDescription="Miscellaneous" Serialized="N" SerialNumbers="" Dropshipped="Y" LineNumber="1" ShipmentMethod="USPS Priority" PurchaseHeaderTaxGroup="Standard VAT" TaxCodeXref="T1" TaxRate="" TaxCode="" TaxAgencyXref="" />
    	</PurchaseTransaction>
    	<PurchaseTransaction DocumentNumber="23" DocumentDate="2015-03-18" PurchaseDate="2015-03-18" VendorName="ConnectWise" VendorNumber="CW0001" VendorAccountNumber="CW0001" VendorInvoiceNumber="" VendorInvoiceDate="2015-03-18" FreightAmount="" FreightPackingSlip="23" APAccountNumber="9000" Class="" ContactName="Arnie Bellini" SiteName="Main" AddressLine1="2803 W Busch Blvd" AddressLine2="Suite 204" AddressLine3="Tampa, FL 33618" City="Tampa" State="FL" PostalCode="33618" Country="" CountryCode="" PhoneNumber="8139357100" Description="Purchase" Memo="PO #23, Packing Slip: 23" BillingTerms="Net 10" CurrencyID="FRF" PackingSlip="23" BillingTermsXref="Net 10" CompanyType="Vendor" TaxCode="1" TaxGroup="Standard VAT" TaxGroupRate="20.000000" TaxAgencyXref="" StateTaxXref="T1" CountyTaxXref="" CityTaxXref="" ShipToCompanyName="" ShipToCompanyAccountNumber="CW0001" ShipToCompanyType="" ShipToContactName="" ShipToSiteName="" ShipToAddressLine1="" ShipToAddressLine2="" ShipToAddressLine3="" ShipToCity="" ShipToState="" ShipToPostalCode="" ShipToCountry="" ShipToCountryCode="" ShipToPhoneNumber="" ShipToTaxGroup="" Dropshipped="N" DueDays="10" UseAvalara="N" PurchaseHeaderTaxGroup="Standard VAT" PurchaseHeaderTaxable="N" PurchaseHeaderFreightTaxable="N" PurchaseInformation="PO #23, Packing Slip: 23" Total="1110.00">
    		<PurchaseDetail DocumentDate="3/18/2015 12:15:16 PM" AccountNumber="4000" Class="" Cost="1110.00" CostAccountNumber="0000" InventoryAccountNumber="0000" SalesCode="0000" Taxable="N" ItemID="System Support" Quantity="-555.00" ItemPrice="250.00" ItemCost="2.00" Total="-1110.00" Description="Purchase" GLEntryRecID="1519" GLTypeID="RP" GLItemID="" ItemTypeXref="" InventoryXref="0000" CogsXref="0000" SalesDescription="Systems Support&amp;#xD;&amp;#xA;&amp;#xD;&amp;#xA;- Network File Server covered&amp;#xD;&amp;#xA;- Network Tape Backup covered&amp;#xD;&amp;#xA;- File Server UPS covered&amp;#xD;&amp;#xA;- Network Adapters covered&amp;#xD;&amp;#xA;- Network Workstation Connections&amp;#xD;&amp;#xA;     All Network hardware cabling to allow proper functioning of &amp;#xD;&amp;#xA;     the Workstation on the Local Area Network&amp;#xD;&amp;#xA;- All Network Concentrators/HUBs covered&amp;#xD;&amp;#xA;- All Network Print Server covered&amp;#xD;&amp;#xA;- All Network cabling covered&amp;#xD;&amp;#xA;- All Network Printer cabling covered&amp;#xD;&amp;#xA;- Extended Warranty &amp; Onsite Repair" ItemDescription="System Support" Memo="System Support" TaxNote="" VendorAccountNumber="CW0001" VendorNumber="CW0001" CurrencyID="FRF" UomName="Month" PriceLevelXref="SERVICE" LocationXref="DEFAULT" BinDescription="Default" WarehouseSiteName="" WarehouseAddressLine1="" WarehouseAddressLine2="" WarehouseCity="" WarehouseState="" WarehouseZip="" WarehouseCountry="" WarehouseCountryCode="" UomScheduleXref="DEFAULT" SubCatDescription="Managed Services" Serialized="N" SerialNumbers="" Dropshipped="N" LineNumber="1" ShipmentMethod="" PurchaseHeaderTaxGroup="Standard VAT" TaxCodeXref="T9" TaxRate="" TaxCode="" TaxAgencyXref="" />
    	</PurchaseTransaction>
    </PurchaseTransactions>
    </GLExport>
```