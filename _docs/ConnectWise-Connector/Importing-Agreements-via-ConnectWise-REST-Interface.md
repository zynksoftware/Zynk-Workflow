---
slug: importing-agreements-via-connectwise-rest-interface
title: Importing Agreements via ConnectWise REST Interface
---
This task will import agreements into ConnectWise from an XML file. See below for a sample input file. 

Agreements are created/updated based on the following rules:
* If an `<id>` is specified, the task will update the agreement with this ID.
* If an `<externalId>` is specified, and a corresponding entry is found in Zynk's truth table, the task will update the agreement with this ID.
* If one or more `<lookup>` elements have been specified, Zynk will search for a match based on each one in turn, and will update the first matching agreement it finds.
* If none of the above conditions are met, the task will create a new company.

When updating existing companies, only writeable fields specified in the input file will be updated. Any other fields will keep their existing values.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the file to output any agreements that failed to import. The error messages will be included in the file.

### Input File
_Required_  
The name of the file containing the agreements to upload to ConnectWise. A sample file is provided below.

### Success File
_Required_  
The name of the file to output any successfully imported agreements to.

### Prevent Reprocessing
_Required_  
Set this option to 'True' to prevent the same agreement being processed more than once by Zynk. An `<externalId>` must be provided in the input file for this to work.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Agreements xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Agreement>
    <id>1</id>
    <externalId />
    <lookups>
      <lookup>
        <matches>
          <match>
            <type>Field</type><!-- Field | ChildField | CustomField -->
            <fieldName>name</fieldName>
            <comparison>Equals</comparison><!-- Equals | Contains | GreaterThan | GreaterThanOrEqual | In | Like | LessThan | LessThanOrEqual | NotEqual | NotContains | NotIn | NotLike | IsNull -->
            <valueType>String</valueType><!-- String | Bool | DateTime | Numeric -->
            <value>Gold Rate</value>
            <values><!-- Used in conjunction with 'In' and 'NotIn' comparisons only -->
              <value>Gold Rate</value>
            </values>
          </match>
        </matches>
        <orderBy>
          <fieldName>name</fieldName>
          <direction>Ascending</direction><!-- Ascending | Descending -->
        </orderBy>
        <type>One</type><!-- One | First -->
      </lookup>
    </lookups>
    <name>Gold Rate</name>
    <type>
      <id>5</id>
      <name>Block Time - One time</name>
    </type>
    <company>
      <id>24</id>
      <name>Wild Eagle, Inc.</name>
      <identifier>WildEagleInc</identifier>
    </company>
    <contact>
      <id>70</id>
      <name>Gregg Kegle</name>
    </contact>
    <customerPO />
    <restrictLocationFlag>false</restrictLocationFlag>
    <restrictDepartmentFlag>false</restrictDepartmentFlag>
    <startDate>2005-04-26T00:00:00Z</startDate>
    <endDate xsi:nil="true" />
    <noEndingDateFlag>true</noEndingDateFlag>
    <cancelledFlag>false</cancelledFlag>
    <dateCancelled xsi:nil="true" />
    <reasonCancelled />
    <workOrder />
    <internalNotes>gets guaranteed rate of $100 per hour for all work performed under this agreement.  See custom rates on the Work Role and Work Type tabs.  This agreement only covers time.  Expenses and products will be billed seperately.</internalNotes>
    <applicationUnits>Amount</applicationUnits>
    <applicationLimit>10000.00</applicationLimit>
    <applicationCycle xsi:nil="true" />
    <applicationUnlimitedFlag>false</applicationUnlimitedFlag>
    <oneTimeFlag>true</oneTimeFlag>
    <coverAgreementTime>true</coverAgreementTime>
    <coverAgreementProduct>false</coverAgreementProduct>
    <coverAgreementExpense>false</coverAgreementExpense>
    <coverSalesTax>false</coverSalesTax>
    <carryOverUnused>false</carryOverUnused>
    <allowOverruns>true</allowOverruns>
    <expiredDays>0</expiredDays>
    <limit>10</limit>
    <expireWhenZero>true</expireWhenZero>
    <chargeToFirm>false</chargeToFirm>
    <employeeCompRate>Hourly</employeeCompRate>
    <employeeCompNotExceed xsi:nil="true" />
    <compHourlyRate>0.00</compHourlyRate>
    <compLimitAmount>0.00</compLimitAmount>
    <billOneTimeFlag>true</billOneTimeFlag>
    <invoicingCycle>CalendarYear</invoicingCycle>
    <billAmount>10000.00</billAmount>
    <taxable>false</taxable>
    <prorateFirstBill>0.00</prorateFirstBill>
    <billStartDate>2005-04-26T00:00:00Z</billStartDate>
    <restrictDownPayment>true</restrictDownPayment>
    <prorateFlag>false</prorateFlag>
    <invoiceDescription>Gold Plan Prepaid Services:
This plan gives you a guaranteed rate of $100 per hour for all work performed against this agreement.
</invoiceDescription>
    <topComment>true</topComment>
    <bottomComment>false</bottomComment>
    <billTime>Billable</billTime>
    <billExpenses>Billable</billExpenses>
    <billProducts>Billable</billProducts>
    <billableTimeInvoice>true</billableTimeInvoice>
    <billableExpenseInvoice>true</billableExpenseInvoice>
    <billableProductInvoice>true</billableProductInvoice>
    <currency>
      <id>4</id>
      <name>French Francs</name>
      <symbol>FFr</symbol>
      <isoCode>EUR</isoCode>
    </currency>
    <periodType xsi:nil="true" />
    <autoInvoiceFlag xsi:nil="true" />
    <customFields>
      <customField>
        <id>13</id>
        <caption>Amethyst Start Date</caption>
        <type>Date</type>
        <entryMethod>EntryField</entryMethod>
        <numberOfDecimals>0</numberOfDecimals>
      </customField>
    </customFields>
  </Agreement>
</Agreements>
```
