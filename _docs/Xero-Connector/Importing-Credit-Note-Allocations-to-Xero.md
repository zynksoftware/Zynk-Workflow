---
slug: importing-credit-note-allocations-to-xero
redirect_from: "/article/907-uploading-credit-note-allocations-to-xero"
title: Importing Credit Note Allocations to Xero
---


This task will create new credit note allocations in Xero using an XML file.


## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Fail File
_Required_  
The file to save failed record imports to.

### Input File
_Required_  
The file containing the bank transactions to upload to Xero.

### Success File
_Required_  
The file to save successful record imports to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once, based on the ExternalId provided in the input XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample input file containing a credit note allocation. It shows the minimum amount of information required to create a credit note allocation in Xero:


```xml
<?xml version="1.0"?>
<ArrayOfXeroCreditNoteAllocation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <XeroCreditNoteAllocation>
    <ExternalId>2053</ExternalId>
    <CreditNote>
      <Id>ccb9278a-87e5-4867-a350-a806bfc672bd</Id>
    </CreditNote>
    <Invoice>
      <Id>d1409f1d-8d9a-4685-9213-fba255db79e5</Id>
    </Invoice>
    <AppliedAmount>162.25</AppliedAmount>
  </XeroCreditNoteAllocation>
</ArrayOfXeroCreditNoteAllocation>
```