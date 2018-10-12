---
slug: exporting-members-from-connectwise-rest-interface
title: Exporting Members from ConnectWise REST Interface
---
This task will export members from ConnectWise in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Export Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'New', only members created after this date will be exported. This date will update automatically each time the task runs, to ensure only new members are exported each time.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only members updated after this date will be downloaded. This date will update automatically each time the task runs, to ensure only modified members are exported each time.

### Export Settings > Export Modified, New or All Records
_Required_  
Choose which records should be downloaded. The available options are:

* __Modified__ - Only records updated after the date shown in the 'Date Modified' setting will be downloaded.
* __New__ - Only records created after the date shown in the 'Date Created' setting will be downloaded.
* __All__ - All records will be downloaded, regardless of when they were created or updated.

### Export Settings > Page Size
_Required_  
The number of records to include in each page of results. Defaults to 100. Increasing this value will reduce the number of requests made to the API. The maximum value is 1000.

### Output File
_Required_  
The name of the file to export the members to.

### References To Fetch
_Optional_  
The exported data may include fields which reference other records in ConnectWise. If you specify the reference field names here, and the task will fetch the related records and include them in the exported data. The supported fields are listed below: 

* reportsTo
* timeApprover
* expenseApprover

### Where Settings > Child Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding standard fields which are part of an array.

### Where Settings > Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding standard fields.

### Where Settings > Custom Field Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding custom fields.

### Where Settings > Condition > Comparison
_Required_  
The following types of filter are available:

* __Contains__ - Returns records where the field contains the specified value.
* __Equal__ - Returns records where the field matches the specified value.
* __GreaterThan__ - Returns records where the field is greater than the specified value.
* __GreaterThanOrEqual__ - Returns records where the field is greater than or equal to the specified value.
* __In__ - Returns records where the field matches one of the specified values.
* __Like__ - Returns records where the field contains the specified value.
* __LessThan__ - Returns records where the field is less than the specified value.
* __LessThanOrEqual__ - Returns records where the field is less than or equal to the specified value.
* __NotContains__ - Returns records where the field does not contain the specified value.
* __NotEqual__ - Returns records where the field does not match the specified value.
* __NotIn__ - Returns records where the field does not match one of the specified values.
* __NotLike__ - Returns records where the field does not contain the specified value.

### Where Settings > Condition > Field
_Required_  
The name of the field the condition is to be based upon. The name should match the API field name, as seen in the output file. If using a reference field, include the name of the reference field followed by a slash, then the field to filter on. e.g. `defaultContact/name`

### Filter Groups > Condition > Logic Operator
_Optional_  
The logic operator to use with the next condition when building the where clause. Choose from:

* __And__ - Will return records which meet all of the conditions specified.
* __Or__ - Will return records which meet at least one of the conditions specified.

### Filter Groups > Condition > Value
_Optional_  
The value the filter is to be based upon.

* String values should be surrounded by quotes. e.g. `"John"`
* Boolean values should be specified as either `True` or `False`, with no quotes.
* Datetime values should be specified in ISO8601 format, surrounded by square brackets. e.g. `[2000-01-31T14:51:00Z]`
* Null is specified as `null`.
* When using the In or NotIn comparison, specify a comma separated list of values surrounded by brackets. e.g. `("John", "Ben")`

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Members xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Member>
    <id>176</id>
    <externalId />
    <_info>
      <lastUpdated>2014-05-01T14:32:57Z</lastUpdated>
      <updatedBy>Admin1</updatedBy>
    </_info>
    <identifier>Admin1</identifier>
    <firstName>Training</firstName>
    <lastName>Admin1</lastName>
    <licenseClass>F</licenseClass>
    <disableOnlineFlag>false</disableOnlineFlag>
    <enableMobileFlag>false</enableMobileFlag>
    <vendorNumber>ZARAR</vendorNumber>
    <timeZone>
      <id>6</id>
      <name>England</name>
    </timeZone>
    <serviceBoardTeamIds>
      <int>25</int>
      <int>26</int>
    </serviceBoardTeamIds>
    <enableMobileGpsFlag>false</enableMobileGpsFlag>
    <inactiveFlag>false</inactiveFlag>
    <lastLogin>2018-08-22T08:04:36Z</lastLogin>
    <officeEmail>test@test.com</officeEmail>
    <officePhone>(813) 111-1111</officePhone>
    <defaultEmail>Office</defaultEmail>
    <defaultPhone>Office</defaultPhone>
    <securityRole>
      <id>63</id>
      <name>Admin</name>
    </securityRole>
    <adminFlag>true</adminFlag>
    <structureLevel>
      <id>1</id>
      <name>Corporate</name>
    </structureLevel>
    <securityLocation>
      <id>38</id>
      <name>Corporate</name>
    </securityLocation>
    <defaultLocation>
      <id>2</id>
      <name>Tampa Office</name>
    </defaultLocation>
    <defaultDepartment>
      <id>10</id>
      <name>Professional Services</name>
    </defaultDepartment>
    <restrictLocationFlag>false</restrictLocationFlag>
    <restrictDepartmentFlag>false</restrictDepartmentFlag>
    <workRole>
      <id>11</id>
      <name>System Engineer</name>
    </workRole>
    <timeApprover>
      <id>176</id>
      <name>Training Admin1</name>
      <identifier>Admin1</identifier>
    </timeApprover>
    <expenseApprover>
      <id>176</id>
      <name>Training Admin1</name>
      <identifier>Admin1</identifier>
    </expenseApprover>
    <billableForecast>75</billableForecast>
    <dailyCapacity>8</dailyCapacity>
    <hourlyCost>0</hourlyCost>
    <hourlyRate xsi:nil="true" />
    <includeInUtilizationReportingFlag>false</includeInUtilizationReportingFlag>
    <requireExpenseEntryFlag>false</requireExpenseEntryFlag>
    <requireTimeSheetEntryFlag>false</requireTimeSheetEntryFlag>
    <requireStartAndEndTimeOnTimeEntryFlag>false</requireStartAndEndTimeOnTimeEntryFlag>
    <allowInCellEntryOnTimeSheet>false</allowInCellEntryOnTimeSheet>
    <enterTimeAgainstCompanyFlag>true</enterTimeAgainstCompanyFlag>
    <allowExpensesEnteredAgainstCompaniesFlag>true</allowExpensesEnteredAgainstCompaniesFlag>
    <timeReminderEmailFlag>false</timeReminderEmailFlag>
    <daysTolerance>1</daysTolerance>
    <minimumHours>8</minimumHours>
    <timeSheetStartDate>2010-07-16T00:00:00Z</timeSheetStartDate>
    <hireDate>2010-07-16T00:00:00Z</hireDate>
    <restrictServiceDefaultLocationFlag>false</restrictServiceDefaultLocationFlag>
    <restrictServiceDefaultDepartmentFlag>false</restrictServiceDefaultDepartmentFlag>
    <excludedServiceBoardIds />
    <restrictProjectDefaultLocationFlag>false</restrictProjectDefaultLocationFlag>
    <restrictProjectDefaultDepartmentFlag>false</restrictProjectDefaultDepartmentFlag>
    <excludedProjectBoardIds />
    <scheduleCapacity>8</scheduleCapacity>
    <restrictScheduleFlag>false</restrictScheduleFlag>
    <hideMemberInDispatchPortalFlag>false</hideMemberInDispatchPortalFlag>
    <salesDefaultLocation>
      <id>39</id>
      <name>My Accounts</name>
    </salesDefaultLocation>
    <restrictDefaultSalesTerritoryFlag>false</restrictDefaultSalesTerritoryFlag>
    <warehouse>
      <id>1</id>
      <name>Default</name>
    </warehouse>
    <warehouseBin>
      <id>1</id>
      <name>Default</name>
    </warehouseBin>
    <restrictDefaultWarehouseFlag>false</restrictDefaultWarehouseFlag>
    <restrictDefaultWarehouseBinFlag>false</restrictDefaultWarehouseBinFlag>
    <calendarSyncIntegrationFlag>false</calendarSyncIntegrationFlag>
    <enableLdapAuthenticationFlag>false</enableLdapAuthenticationFlag>
    <companyActivityTabFormat>SummaryList</companyActivityTabFormat>
    <invoiceTimeTabFormat>SummaryList</invoiceTimeTabFormat>
    <invoiceScreenDefaultTabFormat>ShowInvoicingTab</invoiceScreenDefaultTabFormat>
    <invoicingDisplayOptions>RemainOnInvoicingScreen</invoicingDisplayOptions>
    <agreementInvoicingDisplayOptions>ShowRecentInvoices</agreementInvoicingDisplayOptions>
    <timebasedOneTimePasswordActivated>false</timebasedOneTimePasswordActivated>
  </Member>
</Members>
```
