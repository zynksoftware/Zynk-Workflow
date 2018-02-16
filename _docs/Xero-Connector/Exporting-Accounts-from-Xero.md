---
slug: exporting-accounts-from-xero
redirect_from: "/article/343-downloading-accounts-from-xero"
title: Exporting Accounts from Xero
---


This task will download accounts from Xero in XML format.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Filter
_Optional_  
Specify criteria to filter the accounts on e.g. 	`Type == "BANK" AND Name.Contains("Business")`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


Sample output file showing two accounts:

```xml
<?xml version="1.0"?>
    <ArrayOfXeroAccount>
      <XeroAccount>
        <Id>bd9e85e0-0478-433d-ae9f-0b3c4f04bfe4</Id>
        <Code>090</Code>
        <Name>Business Bank Account</Name>
        <Status>Active</Status>
        <Type>Bank</Type>
        <TaxType>NONE</TaxType>
        <Class>Asset</Class>
        <SystemAccount>Debtors</SystemAccount>
        <EnablePaymentsToAccount>false</EnablePaymentsToAccount>
        <ShowInExpenseClaims>false</ShowInExpenseClaims>
        <BankAccountNumber>990404987654321</BankAccountNumber>
        <CurrencyCode>GBP</CurrencyCode>
        <ReportingCode>ASS</ReportingCode>
        <ReportingCodeName>Assets</ReportingCodeName>
        <HasAttachments>false</HasAttachments>
      </XeroAccount>
      <XeroAccount>
        <Id>a8d6fb1a-8c5d-4683-90ce-bf9d28fc62ba</Id>
        <Code>091</Code>
        <Name>Business Savings Account</Name>
        <Status>Active</Status>
        <Type>Bank</Type>
        <TaxType>NONE</TaxType>
        <Class>Asset</Class>
        <SystemAccount>Debtors</SystemAccount>
        <EnablePaymentsToAccount>false</EnablePaymentsToAccount>
        <ShowInExpenseClaims>false</ShowInExpenseClaims>
        <BankAccountNumber>890303876543210</BankAccountNumber>
        <CurrencyCode>GBP</CurrencyCode>
        <ReportingCode>ASS</ReportingCode>
        <ReportingCodeName>Assets</ReportingCodeName>
        <HasAttachments>false</HasAttachments>
      </XeroAccount>
    </ArrayOfXeroAccount>
```