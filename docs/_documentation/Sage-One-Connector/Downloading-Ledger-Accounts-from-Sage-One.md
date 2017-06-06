---
slug: downloading-ledger-accounts-from-sage-one
redirect_from: "/article/852-download-ledger-accounts"
title: Downloading Ledger Accounts from Sage One
---
This task will download Ledger Accounts from your instance of Sage One.

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
<ArrayOfLedgerAccount xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <LedgerAccount>
    <SageOneRecordId>2654253</SageOneRecordId>
    <Name>Current</Name>
    <NominalCode>1200</NominalCode>
  </LedgerAccount>
  <LedgerAccount>
    <SageOneRecordId>2654254</SageOneRecordId>
    <Name>Cash in Hand</Name>
    <NominalCode>1210</NominalCode>
  </LedgerAccount>
  <LedgerAccount>
    <SageOneRecordId>2654255</SageOneRecordId>
    <Name>Assets - Cost</Name>
    <NominalCode>1</NominalCode>
  </LedgerAccount>
</ArrayOfLedgerAccount>
```