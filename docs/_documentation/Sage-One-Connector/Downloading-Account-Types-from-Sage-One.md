---
slug: downloading-account-types-from-sage-one
redirect_from: "/article/848-download-account-types"
title: Downloading Account Types from Sage One
---
This task will download Account Types from your instance of Sage One. 

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
<ArrayOfAccountType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <AccountType>
    <SageOneRecordId>1</SageOneRecordId>
    <Name>Current</Name>
  </AccountType>
  <AccountType>
    <SageOneRecordId>2</SageOneRecordId>
    <Name>Savings</Name>
  </AccountType>
  <AccountType>
    <SageOneRecordId>3</SageOneRecordId>
    <Name>Credit Card</Name>
  </AccountType>
  <AccountType>
    <SageOneRecordId>5</SageOneRecordId>
    <Name>Cash in Hand</Name>
  </AccountType>
  <AccountType>
    <SageOneRecordId>6</SageOneRecordId>
    <Name>Loan</Name>
  </AccountType>
  <AccountType>
    <SageOneRecordId>7</SageOneRecordId>
    <Name>Other</Name>
  </AccountType>
</ArrayOfAccountType>
```