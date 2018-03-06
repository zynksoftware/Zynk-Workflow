---
slug: validating-tax-numbers
redirect_from: "/article/validating-tax-numbers"
title: Validating Tax Numbers
---

This task will validate tax numbers which are provided, and save the output to an XML file.

## Settings
### Input File
_Required_  
The XML file which contains the tax numbers to be validated.

### Output File
_Required_  
The XML file to save the list of records to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<VatNumbers>
    <VatNumber>
        <Country>GB</Country>
        <Number>796576359</Number>
    </VatNumber>
</VatNumbers>
```

Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<VatNumbers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <VatNumber>
    <Country>GB</Country>
    <Number>796576359</Number>
    <Valid>true</Valid>
    <Company>ZYNK SOFTWARE LIMITED !! INTERNETWARE</Company>
    <Address>NELSON HOUSE
THE FLEMING BUSINESS CENTRE
JESMOND
NEWCASTLE UPONTYNE

NE2 3AE</Address>
    <Error />
  </VatNumber>
</VatNumbers>
```
