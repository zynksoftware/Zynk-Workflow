---
slug: downloading-period-types-from-sage-one
redirect_from: "/article/853-download-period-types"
title: Downloading Period Types from Sage One
---
This task will download Period Types from your instance of Sage One.

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
<ArrayOfPeriodRate xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PeriodRate>
    <SageOneRecordId>1</SageOneRecordId>
    <PeriodRateType>Annually</PeriodRateType>
  </PeriodRate>
  <PeriodRate>
    <SageOneRecordId>2</SageOneRecordId>
    <PeriodRateType>Daily</PeriodRateType>
  </PeriodRate>
  <PeriodRate>
    <SageOneRecordId>3</SageOneRecordId>
    <PeriodRateType>Hourly</PeriodRateType>
  </PeriodRate>
  <PeriodRate>
    <SageOneRecordId>4</SageOneRecordId>
    <PeriodRateType>Monthly</PeriodRateType>
  </PeriodRate>
  <PeriodRate>
    <SageOneRecordId>5</SageOneRecordId>
    <PeriodRateType>Quarterly</PeriodRateType>
  </PeriodRate>
  <PeriodRate>
    <SageOneRecordId>6</SageOneRecordId>
    <PeriodRateType>Weekly</PeriodRateType>
  </PeriodRate>
  <PeriodRate>
    <SageOneRecordId>7</SageOneRecordId>
    <PeriodRateType>FixedRate</PeriodRateType>
  </PeriodRate>
</ArrayOfPeriodRate>
```