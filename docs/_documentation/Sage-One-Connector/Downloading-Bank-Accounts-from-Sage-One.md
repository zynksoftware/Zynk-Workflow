---
slug: downloading-bank-accounts-from-sage-one
redirect_from: "/article/849-download-bank-accounts"
title: Downloading Bank Accounts from Sage One
---
This task will download Bank Accounts from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Download Type
_Required_  
Select All, New or Modified.

### Record Id
_Optional_  
Optionally download a specific record by specifying the Sage One id.

### Output File
_Required_  
The file to save the downloaded records to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below.
```xml
<?xml version="1.0"?>
<ArrayOfBankAccount xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <BankAccount>
    <SageOneRecordId>124211</SageOneRecordId>
    <AccountName>Current</AccountName>
    <AccountNumber>TEST01</AccountNumber>
    <AccountType>
      <SageOneRecordId>1</SageOneRecordId>
      <Errors />
      <Name>Current</Name>
    </AccountType>
    <Balance>-179.54</Balance>
    <SortCode>404040</SortCode>
    <Telephone />
    <Email />
    <BankAddress>
      <Address2>123 Test Road</Address2>
      <Town>Test</Town>
      <County>Testishire</County>
      <Postcode>NE30 2DR</Postcode>
    </BankAddress>
  </BankAccount>
  <BankAccount>
    <SageOneRecordId>124212</SageOneRecordId>
    <AccountName>Cash in Hand</AccountName>
    <AccountNumber />
    <AccountType>
      <SageOneRecordId>5</SageOneRecordId>
      <Errors />
      <Name>Cash in Hand</Name>
    </AccountType>
    <Balance>-56</Balance>
    <SortCode />
    <Telephone />
    <Email />
    <BankAddress>
      <Address2 />
      <Town />
      <County />
      <Postcode />
    </BankAddress>
  </BankAccount>
  <BankAccount>
    <SageOneRecordId>345022</SageOneRecordId>
    <AccountName>Test Loan Account</AccountName>
    <AccountNumber>TEST02</AccountNumber>
    <AccountType>
      <SageOneRecordId>6</SageOneRecordId>
      <Errors />
      <Name>Loan</Name>
    </AccountType>
    <Balance>-123.44</Balance>
    <SortCode>404140</SortCode>
    <Telephone />
    <Email />
    <BankAddress>
      <Address2 />
      <Town />
      <County />
      <Postcode />
    </BankAddress>
  </BankAccount>
</ArrayOfBankAccount>
```