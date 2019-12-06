---
slug: exporting-agreements-from-connectwise-rest-interface
title: Exporting Agreements from ConnectWise REST Interface
---
This task will export agreements from ConnectWise in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Export Item Lines
_Required_  
Set to true to include the item lines in the exported data.

### Export Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'New', only purchase orders created after this date will be exported. This date will update automatically each time the task runs, to ensure only new puchase orders are exported each time.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only purchase orders updated after this date will be downloaded. This date will update automatically each time the task runs, to ensure only modified invoices are exported each time.

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
The name of the file to export the purchase orders to.

### References To Fetch
_Optional_  
The exported data may include fields which reference other records in ConnectWise. If you specify the reference field names here, and the task will fetch the related records and include them in the exported data. The supported fields are listed below: 

* type
* company
* contact
* site
* subContractCompany
* subContractContact
* parentAgreement
* billToCompany
* billToCompany
* billToSite
* taxCode
* workRole
* workType
* invoiceTemplate
* currency
* agreementAdditions
* agreementAddition/product

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
<Agreements xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Agreement>
    <id>2</id>
    <externalId />
    <_info>
      <lastUpdated>2012-03-19T20:39:25Z</lastUpdated>
      <updatedBy>Admin1         </updatedBy>
    </_info>
    <name>Managed Services for Angry Fox</name>
    <type>
      <id>3</id>
      <name>Managed Service</name>
      <record>
        <id>3</id>
        <_info>
          <dateEntered>2005-09-13T15:19:07Z</dateEntered>
          <enteredBy>CONVERSION</enteredBy>
          <lastUpdated>2005-09-13T15:19:07Z</lastUpdated>
          <updatedBy>User10</updatedBy>
        </_info>
        <name>Managed Service</name>
        <prefixSuffixOption>Prefix</prefixSuffixOption>
        <defaultFlag>false</defaultFlag>
        <inactiveFlag>false</inactiveFlag>
        <prePaymentFlag>false</prePaymentFlag>
        <invoicePreSuffix xsi:nil="true" />
        <locationId xsi:nil="true" />
        <businessUnitId xsi:nil="true" />
        <restrictLocationFlag>false</restrictLocationFlag>
        <restrictDepartmentFlag>false</restrictDepartmentFlag>
        <slaId xsi:nil="true" />
        <applicationUnits>Hours</applicationUnits>
        <applicationLimit>0.00</applicationLimit>
        <applicationCycle>CalendarMonth</applicationCycle>
        <applicationUnlimitedFlag>true</applicationUnlimitedFlag>
        <oneTimeFlag>false</oneTimeFlag>
        <coverAgreementTimeFlag>true</coverAgreementTimeFlag>
        <coverAgreementProductFlag>false</coverAgreementProductFlag>
        <coverAgreementExpenseFlag>false</coverAgreementExpenseFlag>
        <coverSalesTaxFlag>false</coverSalesTaxFlag>
        <carryOverUnusedFlag>false</carryOverUnusedFlag>
        <allowOverrunsFlag>false</allowOverrunsFlag>
        <expiredDays>0</expiredDays>
        <limit>0</limit>
        <expireWhenZero>false</expireWhenZero>
        <chargeToFirmFlag>false</chargeToFirmFlag>
        <employeeCompRate>Actual</employeeCompRate>
        <compHourlyRate xsi:nil="true" />
        <compLimitAmount xsi:nil="true" />
        <billCycleId xsi:nil="true" />
        <billOneTimeFlag>false</billOneTimeFlag>
        <billTermsId xsi:nil="true" />
        <invoicingCycle>CalendarYear</invoicingCycle>
        <billAmount>0.00</billAmount>
        <taxableFlag>false</taxableFlag>
        <restrictDownPaymentFlag>true</restrictDownPaymentFlag>
        <invoiceDescription />
        <topCommentFlag>false</topCommentFlag>
        <bottomCommentFlag>false</bottomCommentFlag>
        <workType>
          <id>18</id>
          <name>Remote Support</name>
        </workType>
        <projectTypeId xsi:nil="true" />
        <invoiceTemplateSetupId xsi:nil="true" />
        <billTime>Billable</billTime>
        <billExpenses>Billable</billExpenses>
        <billProducts>Billable</billProducts>
        <billableTimeInvoiceFlag>false</billableTimeInvoiceFlag>
        <billableExpenseInvoiceFlag>false</billableExpenseInvoiceFlag>
        <billableProductInvoiceFlag>false</billableProductInvoiceFlag>
        <copyWorkRolesFlag>true</copyWorkRolesFlag>
        <copyWorkTypesFlag>true</copyWorkTypesFlag>
      </record>
    </type>
    <company>
      <id>8</id>
      <name>Angry Fox, Co.</name>
      <record>
        <id>8</id>
        <_info>
          <dateEntered>2005-03-21T15:43:44Z</dateEntered>
          <enteredBy>CONVERSION</enteredBy>
          <lastUpdated>2018-05-08T15:07:00Z</lastUpdated>
          <updatedBy>zynk</updatedBy>
        </_info>
        <identifier>AngryFoxCo</identifier>
        <name>Angry Fox, Co.</name>
        <status>
          <id>1</id>
          <name>Active</name>
        </status>
        <addressLine1>711 N. Franklin St.</addressLine1>
        <city>Detroit</city>
        <state>MI</state>
        <zip>92344</zip>
        <country>
          <id>1</id>
          <name>United States</name>
        </country>
        <phoneNumber>8131782000</phoneNumber>
        <faxNumber>8131782001</faxNumber>
        <website>http://www.AngryFox.com</website>
        <territory>
          <id>41</id>
          <name>Arnie's Accounts</name>
        </territory>
        <marketId xsi:nil="true" />
        <accountNumber>ANGRYF01</accountNumber>
        <defaultContact>
          <id>20</id>
          <name>Robert Storts</name>
        </defaultContact>
        <dateAcquired>2005-03-21T05:00:00Z</dateAcquired>
        <annualRevenue>0.00</annualRevenue>
        <numberOfEmployees xsi:nil="true" />
        <leadSource>Microsoft Tradeshow</leadSource>
        <leadFlag>false</leadFlag>
        <unsubscribeFlag>false</unsubscribeFlag>
        <calendarId xsi:nil="true" />
        <vendorIdentifier>AngryFox1010</vendorIdentifier>
        <taxCode>
          <id>11</id>
          <name>Standard VAT</name>
        </taxCode>
        <billingTerms>
          <id>2</id>
          <name>Net 10</name>
        </billingTerms>
        <billToCompany>
          <id>8</id>
          <name>Angry Fox, Co.</name>
          <identifier>AngryFoxCo</identifier>
        </billToCompany>
        <billingSite>
          <id>31</id>
          <name>Main</name>
        </billingSite>
        <billingContact>
          <id>20</id>
          <name>Robert Storts</name>
        </billingContact>
        <invoiceDeliveryMethod>
          <id>2</id>
          <name>E-Mail</name>
        </invoiceDeliveryMethod>
        <invoiceToEmailAddress>test@test.com</invoiceToEmailAddress>
        <deletedFlag>false</deletedFlag>
        <dateDeleted xsi:nil="true" />
        <mobileGuid>38a5f551-d40d-49e7-99f8-4fb5029df6ea</mobileGuid>
        <customFields>
          <customField>
            <id>3</id>
            <caption>test</caption>
            <type>Text</type>
            <entryMethod>EntryField</entryMethod>
            <numberOfDecimals>0</numberOfDecimals>
          </customField>
          <customField>
            <id>6</id>
            <caption>CustomNumber</caption>
            <type>Number</type>
            <entryMethod>EntryField</entryMethod>
            <numberOfDecimals>2</numberOfDecimals>
          </customField>
          <customField>
            <id>7</id>
            <caption>Salesperson</caption>
            <type>Text</type>
            <entryMethod>List</entryMethod>
            <numberOfDecimals>0</numberOfDecimals>
          </customField>
        </customFields>
      </record>
      <identifier>AngryFoxCo</identifier>
    </company>
    <contact>
      <id>20</id>
      <name>Robert Storts</name>
      <record>
        <id>20</id>
        <_info>
          <lastUpdated>2010-07-19T16:42:32Z</lastUpdated>
          <updatedBy>Admin1</updatedBy>
        </_info>
        <firstName>Robert</firstName>
        <lastName>Storts</lastName>
        <company>
          <id>8</id>
          <name>Angry Fox, Co.</name>
          <identifier>AngryFoxCo</identifier>
        </company>
        <site>
          <id>7</id>
          <name>Main</name>
        </site>
        <inactiveFlag>false</inactiveFlag>
        <defaultMergeContactId xsi:nil="true" />
        <managerContactId xsi:nil="true" />
        <assistantContactId xsi:nil="true" />
        <title>President</title>
        <marriedFlag>false</marriedFlag>
        <childrenFlag>false</childrenFlag>
        <portalSecurityLevel>6</portalSecurityLevel>
        <disablePortalLoginFlag>true</disablePortalLoginFlag>
        <unsubscribeFlag>false</unsubscribeFlag>
        <mobileGuid>59862c1a-fd4b-48c2-84db-3736e82f591e</mobileGuid>
        <defaultBillingFlag>true</defaultBillingFlag>
        <defaultFlag>true</defaultFlag>
        <communicationItems>
          <ContactCommunicationItem>
            <id>47</id>
            <type>
              <id>2</id>
              <_info />
              <name>Direct</name>
            </type>
            <value>8139888241</value>
            <defaultFlag>true</defaultFlag>
            <communicationType>Phone</communicationType>
          </ContactCommunicationItem>
          <ContactCommunicationItem>
            <id>48</id>
            <type>
              <id>1</id>
              <_info />
              <name>Email</name>
            </type>
            <value>test@test.com</value>
            <defaultFlag>true</defaultFlag>
            <communicationType>Email</communicationType>
          </ContactCommunicationItem>
        </communicationItems>
      </record>
    </contact>
    <customerPO />
    <location>
      <id>2</id>
      <name>Tampa Office</name>
      <record>
        <id>2</id>
        <_info>
          <lastUpdated>2005-03-21T11:04:16Z</lastUpdated>
          <updatedBy>zAdmin</updatedBy>
        </_info>
        <ownerLevelId>2</ownerLevelId>
        <structureLevel>
          <id>2</id>
          <name>Location (Level 2)</name>
        </structureLevel>
        <name>Tampa Office</name>
        <reportsTo>
          <id>38</id>
          <name>Corporate</name>
        </reportsTo>
        <calendar>
          <id>1</id>
          <name>Standard Office Hours</name>
        </calendar>
        <locationFlag>true</locationFlag>
        <clientFlag>false</clientFlag>
        <workRoleIds>
          <workRoleId>6</workRoleId>
          <workRoleId>11</workRoleId>
          <workRoleId>16</workRoleId>
          <workRoleId>17</workRoleId>
          <workRoleId>18</workRoleId>
          <workRoleId>21</workRoleId>
        </workRoleIds>
        <departmentIds>
          <departmentId>10</departmentId>
          <departmentId>13</departmentId>
          <departmentId>14</departmentId>
          <departmentId>15</departmentId>
          <departmentId>16</departmentId>
        </departmentIds>
      </record>
    </location>
    <department>
      <id>10</id>
      <name>Professional Services</name>
      <record>
        <id>10</id>
        <_info>
          <lastUpdated>2006-10-11T09:44:55Z</lastUpdated>
          <updatedBy>User1</updatedBy>
        </_info>
        <identifier>Services</identifier>
        <name>Professional Services</name>
      </record>
    </department>
    <restrictLocationFlag>false</restrictLocationFlag>
    <restrictDepartmentFlag>false</restrictDepartmentFlag>
    <startDate>2005-05-01T00:00:00Z</startDate>
    <endDate xsi:nil="true" />
    <noEndingDateFlag>true</noEndingDateFlag>
    <cancelledFlag>false</cancelledFlag>
    <dateCancelled xsi:nil="true" />
    <reasonCancelled />
    <workOrder />
    <internalNotes>This is a monthly agreement for managed services.  An unlimited number hours are available per year for all work done that is entered against the agreement.  The individual services are selected using the Additions tab - these will total up for the monthly billing amount.  
If you need to prorate the first bill and you are using additions, you must enter the prorated amounts in the additions tab and control it with effective dates.  The Prorate first bill? field only overrides the Billing Amount field.
See Agreement Invoice #1 note descriptions from additions
</internalNotes>
    <applicationUnits>Hours</applicationUnits>
    <applicationLimit>0.00</applicationLimit>
    <applicationCycle>ContractYear</applicationCycle>
    <applicationUnlimitedFlag>true</applicationUnlimitedFlag>
    <oneTimeFlag>false</oneTimeFlag>
    <coverAgreementTime>true</coverAgreementTime>
    <coverAgreementProduct>false</coverAgreementProduct>
    <coverAgreementExpense>false</coverAgreementExpense>
    <coverSalesTax>false</coverSalesTax>
    <carryOverUnused>false</carryOverUnused>
    <allowOverruns>false</allowOverruns>
    <expiredDays>0</expiredDays>
    <limit>0</limit>
    <expireWhenZero>false</expireWhenZero>
    <chargeToFirm>false</chargeToFirm>
    <employeeCompRate>Actual</employeeCompRate>
    <employeeCompNotExceed>Billing</employeeCompNotExceed>
    <compHourlyRate>0.00</compHourlyRate>
    <compLimitAmount>0.00</compLimitAmount>
    <billingCycle>
      <id>2</id>
      <name>Monthly</name>
      <record>
        <id>2</id>
        <_info>
          <dateEntered>2004-07-08T13:57:52Z</dateEntered>
          <enteredBy>CONVERSION</enteredBy>
          <lastUpdated>2004-07-08T13:57:52Z</lastUpdated>
          <updatedBy>zadmin</updatedBy>
        </_info>
        <identifier>M</identifier>
        <name>Monthly</name>
        <defaultFlag>true</defaultFlag>
        <billingOptions>Monthly</billingOptions>
      </record>
    </billingCycle>
    <billOneTimeFlag>false</billOneTimeFlag>
    <invoicingCycle>CalendarYear</invoicingCycle>
    <billAmount>0.00</billAmount>
    <taxable>false</taxable>
    <prorateFirstBill>0.00</prorateFirstBill>
    <billStartDate>2005-05-01T00:00:00Z</billStartDate>
    <taxCode>
      <id>11</id>
      <name>Standard VAT</name>
      <record>
        <id>11</id>
        <_info>
          <dateEntered>2013-07-11T13:55:59Z</dateEntered>
          <enteredBy>CONVERSION</enteredBy>
          <lastUpdated>2013-07-11T13:55:59Z</lastUpdated>
          <updatedBy>Admin1</updatedBy>
        </_info>
        <identifier>1</identifier>
        <description>Standard VAT</description>
        <invoiceCaption>VAT</invoiceCaption>
        <country>
          <id>1</id>
          <name>United States</name>
        </country>
        <effectiveDate>2005-05-02T00:00:00Z</effectiveDate>
        <defaultFlag>false</defaultFlag>
        <displayOnInvoiceFlag>false</displayOnInvoiceFlag>
        <canadaCalculateGSTFlag>false</canadaCalculateGSTFlag>
        <levelOneRate>0.200000</levelOneRate>
        <levelOneRateType>Percent</levelOneRateType>
        <levelOneTaxableMax xsi:nil="true" />
        <levelOneCaption>Standard VAT</levelOneCaption>
        <levelOneTaxCodeXref>T1</levelOneTaxCodeXref>
        <levelOneServicesFlag>true</levelOneServicesFlag>
        <levelOneExpensesFlag>true</levelOneExpensesFlag>
        <levelOneProductsFlag>true</levelOneProductsFlag>
        <levelOneApplySingleUnitFlag>false</levelOneApplySingleUnitFlag>
        <levelOneApplySingleUnitMin xsi:nil="true" />
        <levelOneApplySingleUnitMax xsi:nil="true" />
        <levelTwoRate>0.000000</levelTwoRate>
        <levelTwoRateType>Percent</levelTwoRateType>
        <levelTwoTaxableMax xsi:nil="true" />
        <levelTwoServicesFlag>false</levelTwoServicesFlag>
        <levelTwoExpensesFlag>false</levelTwoExpensesFlag>
        <levelTwoProductsFlag>false</levelTwoProductsFlag>
        <levelTwoApplySingleUnitFlag>false</levelTwoApplySingleUnitFlag>
        <levelTwoApplySingleUnitMin xsi:nil="true" />
        <levelTwoApplySingleUnitMax xsi:nil="true" />
        <levelThreeRate>0.000000</levelThreeRate>
        <levelThreeRateType>Percent</levelThreeRateType>
        <levelThreeTaxableMax xsi:nil="true" />
        <levelThreeServicesFlag>false</levelThreeServicesFlag>
        <levelThreeExpensesFlag>false</levelThreeExpensesFlag>
        <levelThreeProductsFlag>false</levelThreeProductsFlag>
        <levelThreeApplySingleUnitFlag>false</levelThreeApplySingleUnitFlag>
        <levelThreeApplySingleUnitMin xsi:nil="true" />
        <levelThreeApplySingleUnitMax xsi:nil="true" />
        <levelFourRate>0.000000</levelFourRate>
        <levelFourRateType>Percent</levelFourRateType>
        <levelFourTaxableMax xsi:nil="true" />
        <levelFourServicesFlag>false</levelFourServicesFlag>
        <levelFourExpensesFlag>false</levelFourExpensesFlag>
        <levelFourProductsFlag>false</levelFourProductsFlag>
        <levelFourApplySingleUnitFlag>false</levelFourApplySingleUnitFlag>
        <levelFourApplySingleUnitMin xsi:nil="true" />
        <levelFourApplySingleUnitMax xsi:nil="true" />
        <levelFiveRate>0.000000</levelFiveRate>
        <levelFiveRateType>Percent</levelFiveRateType>
        <levelFiveTaxableMax xsi:nil="true" />
        <levelFiveServicesFlag>false</levelFiveServicesFlag>
        <levelFiveExpensesFlag>false</levelFiveExpensesFlag>
        <levelFiveProductsFlag>false</levelFiveProductsFlag>
        <levelFiveApplySingleUnitFlag>false</levelFiveApplySingleUnitFlag>
        <levelFiveApplySingleUnitMin xsi:nil="true" />
        <levelFiveApplySingleUnitMax xsi:nil="true" />
        <levelSixRate>0.000000</levelSixRate>
        <levelSixRateType>Percent</levelSixRateType>
        <levelSixTaxableMax xsi:nil="true" />
        <levelSixServicesFlag>false</levelSixServicesFlag>
        <levelSixExpensesFlag>false</levelSixExpensesFlag>
        <levelSixProductsFlag>false</levelSixProductsFlag>
        <levelSixApplySingleUnitFlag>false</levelSixApplySingleUnitFlag>
        <levelSixApplySingleUnitMin xsi:nil="true" />
        <levelSixApplySingleUnitMax xsi:nil="true" />
        <addAllWorkRoles xsi:nil="true" />
        <removeAllWorkRoles xsi:nil="true" />
        <expenseTypeIds>
          <int>5</int>
          <int>6</int>
        </expenseTypeIds>
        <addAllExpenseTypes xsi:nil="true" />
        <removeAllExpenseTypes xsi:nil="true" />
        <addAllProductTypes xsi:nil="true" />
        <removeAllProductTypes xsi:nil="true" />
      </record>
    </taxCode>
    <restrictDownPayment>true</restrictDownPayment>
    <prorateFlag>false</prorateFlag>
    <invoiceDescription />
    <topComment>false</topComment>
    <bottomComment>false</bottomComment>
    <workType>
      <id>18</id>
      <name>Remote Support</name>
      <record>
        <id>18</id>
        <_info>
          <lastUpdated>2004-07-29T13:38:39Z</lastUpdated>
          <updatedBy>zadmin</updatedBy>
        </_info>
        <activityDefaultFlag>false</activityDefaultFlag>
        <addAllAgreementExclusions xsi:nil="true" />
        <billTime>Billable</billTime>
        <costMultiplier>1</costMultiplier>
        <hoursMax>0</hoursMax>
        <hoursMin>0.25</hoursMin>
        <inactiveFlag>false</inactiveFlag>
        <name>Remote Support</name>
        <overallDefaultFlag>false</overallDefaultFlag>
        <rate>1</rate>
        <rateType>Multiplier</rateType>
        <roundBillHoursTo xsi:nil="true" />
        <utilizationFlag>true</utilizationFlag>
      </record>
    </workType>
    <billTime>Billable</billTime>
    <billExpenses>Billable</billExpenses>
    <billProducts>Billable</billProducts>
    <billableTimeInvoice>false</billableTimeInvoice>
    <billableExpenseInvoice>false</billableExpenseInvoice>
    <billableProductInvoice>false</billableProductInvoice>
    <currency>
      <id>4</id>
      <name>French Francs</name>
      <record>
        <id>4</id>
        <_info>
          <dateEntered>1999-06-21T12:03:44Z</dateEntered>
          <enteredBy>CONVERSION</enteredBy>
          <lastUpdated>2019-06-13T12:43:44Z</lastUpdated>
          <updatedBy>CURR_CONVERSION</updatedBy>
        </_info>
        <currencyIdentifier>FRF</currencyIdentifier>
        <name>French Francs</name>
        <symbol>FFr</symbol>
        <displayIdFlag>false</displayIdFlag>
        <displaySymbolFlag>false</displaySymbolFlag>
      </record>
      <symbol>FFr</symbol>
      <isoCode>EUR</isoCode>
    </currency>
    <periodType xsi:nil="true" />
    <autoInvoiceFlag>false</autoInvoiceFlag>
    <customFields>
      <customField>
        <id>13</id>
        <caption>Amethyst Start Date</caption>
        <type>Date</type>
        <entryMethod>EntryField</entryMethod>
        <numberOfDecimals>0</numberOfDecimals>
      </customField>
      <customField>
        <id>14</id>
        <caption>Activity Creation</caption>
        <type>Date</type>
        <entryMethod>EntryField</entryMethod>
        <numberOfDecimals>0</numberOfDecimals>
      </customField>
      <customField>
        <id>15</id>
        <caption>Revision Number</caption>
        <type>Number</type>
        <entryMethod>EntryField</entryMethod>
        <numberOfDecimals>0</numberOfDecimals>
      </customField>
    </customFields>
    <agreementAdditions>
      <agreementAddition>
        <id>1</id>
        <_info>
          <lastUpdated>2019-11-25T13:18:23Z</lastUpdated>
          <updatedBy>Admin1</updatedBy>
        </_info>
        <product>
          <id>745</id>
          <record>
            <id>745</id>
            <_info>
              <lastUpdated>2005-05-26T14:27:29Z</lastUpdated>
              <updatedBy>user10</updatedBy>
            </_info>
            <identifier>Web Site Service</identifier>
            <description>Web Site Service</description>
            <inactiveFlag>false</inactiveFlag>
            <subcategory>
              <id>38</id>
              <name>Managed Services</name>
            </subcategory>
            <type>
              <id>33</id>
              <name>Fixed Cost Service</name>
            </type>
            <productClass>NonInventory</productClass>
            <serializedFlag>false</serializedFlag>
            <serializedCostFlag>false</serializedCostFlag>
            <phaseProductFlag>false</phaseProductFlag>
            <unitOfMeasure>
              <id>14</id>
              <name>Month</name>
            </unitOfMeasure>
            <minStockLevel>0</minStockLevel>
            <price>1000.000000</price>
            <cost>0.000000</cost>
            <taxableFlag>false</taxableFlag>
            <customerDescription>Managed Web Site Service
Dedicated Website Hosting Service
- Domain Name Service Services
- Domain Name Hostting Services
- 8 IP Address
- 100 GB Transfer per month
- Intel Xeon 2.4 GHz w/HyperTHreading
- Windows 2003 Server
- Windows 2003 Terminal Services


Managed Services
- Site monitoring 24 x 7
- Complete Hardware Maintenance
- Security Updates
- Operating System Updates
- Server Reboot- Server Diagnostics</customerDescription>
            <recurringFlag>false</recurringFlag>
            <recurringRevenue xsi:nil="true" />
            <recurringCost xsi:nil="true" />
            <recurringOneTimeFlag>false</recurringOneTimeFlag>
            <dateEntered>2005-05-26T14:27:29Z</dateEntered>
            <category>
              <id>18</id>
              <name>Managed Services</name>
            </category>
          </record>
          <identifier>Web Site Service</identifier>
        </product>
        <quantity>3.00</quantity>
        <lessIncluded>0.00</lessIncluded>
        <unitPrice>1000.000000</unitPrice>
        <unitCost xsi:nil="true" />
        <billCustomer>Billable</billCustomer>
        <effectiveDate>2005-05-01T00:00:00Z</effectiveDate>
        <cancelledDate xsi:nil="true" />
        <taxableFlag>false</taxableFlag>
        <serialNumber>000000100</serialNumber>
        <invoiceDescription>Managed Web Site Service
Dedicated Website Hosting Service
- Domain Name Service Services
- Domain Name Hostting Services
- 8 IP Address
- 100 GB Transfer per month
- Intel Xeon 2.4 GHz w/HyperTHreading
- Windows 2003 Server
- Windows 2003 Terminal Services


Managed Services
- Site monitoring 24 x 7
- Complete Hardware Maintenance
- Security Updates
- Operating System Updates
- Server Reboot- Server Diagnostics</invoiceDescription>
        <purchaseItemFlag>false</purchaseItemFlag>
        <specialOrderFlag>false</specialOrderFlag>
        <agreementId>2</agreementId>
        <description>Web Site Service</description>
        <billedQuantity>3.00</billedQuantity>
        <uom>Month</uom>
        <extPrice>3000.000000</extPrice>
        <extCost>0.000000</extCost>
        <sequenceNumber>1.00</sequenceNumber>
        <margin>3000.000000</margin>
        <prorateCost>0.000000</prorateCost>
        <proratePrice>0.000000</proratePrice>
        <extendedProrateCost>0.000000</extendedProrateCost>
        <extendedProratePrice>0.000000</extendedProratePrice>
        <prorateCurrentPeriodFlag>false</prorateCurrentPeriodFlag>
        <agreementStatus>Active</agreementStatus>
      </agreementAddition>
      <agreementAddition>
        <id>2</id>
        <_info>
          <lastUpdated>2005-05-19T19:52:51Z</lastUpdated>
          <updatedBy>user10</updatedBy>
        </_info>
        <product>
          <id>747</id>
          <record>
            <id>747</id>
            <_info>
              <lastUpdated>2015-03-18T16:15:26Z</lastUpdated>
              <updatedBy>Admin1</updatedBy>
            </_info>
            <identifier>System Support</identifier>
            <description>System Support</description>
            <inactiveFlag>false</inactiveFlag>
            <subcategory>
              <id>38</id>
              <name>Managed Services</name>
            </subcategory>
            <type>
              <id>33</id>
              <name>Fixed Cost Service</name>
            </type>
            <productClass>NonInventory</productClass>
            <serializedFlag>false</serializedFlag>
            <serializedCostFlag>false</serializedCostFlag>
            <phaseProductFlag>false</phaseProductFlag>
            <unitOfMeasure>
              <id>14</id>
              <name>Month</name>
            </unitOfMeasure>
            <minStockLevel>0</minStockLevel>
            <price>250.000000</price>
            <cost>2.000000</cost>
            <taxableFlag>false</taxableFlag>
            <customerDescription>Systems Support

- Network File Server covered
- Network Tape Backup covered
- File Server UPS covered
- Network Adapters covered
- Network Workstation Connections
     All Network hardware cabling to allow proper functioning of 
     the Workstation on the Local Area Network
- All Network Concentrators/HUBs covered
- All Network Print Server covered
- All Network cabling covered
- All Network Printer cabling covered
- Extended Warranty &amp; Onsite Repair
  </customerDescription>
            <recurringFlag>false</recurringFlag>
            <recurringRevenue xsi:nil="true" />
            <recurringCost xsi:nil="true" />
            <recurringOneTimeFlag>false</recurringOneTimeFlag>
            <dateEntered>2015-03-18T16:15:26Z</dateEntered>
            <category>
              <id>18</id>
              <name>Managed Services</name>
            </category>
          </record>
          <identifier>System Support</identifier>
        </product>
        <quantity>1.00</quantity>
        <lessIncluded>0.00</lessIncluded>
        <unitPrice>250.000000</unitPrice>
        <unitCost xsi:nil="true" />
        <billCustomer>Billable</billCustomer>
        <effectiveDate>2005-05-01T00:00:00Z</effectiveDate>
        <cancelledDate xsi:nil="true" />
        <taxableFlag>false</taxableFlag>
        <invoiceDescription>Systems Support

- Network File Server covered
- Network Tape Backup covered
- File Server UPS covered
- Network Adapters covered
- Network Workstation Connections
     All Network hardware cabling to allow proper functioning of 
     the Workstation on the Local Area Network
- All Network Concentrators/HUBs covered
- All Network Print Server covered
- All Network cabling covered
- All Network Printer cabling covered
- Extended Warranty &amp; Onsite Repair
  </invoiceDescription>
        <purchaseItemFlag>false</purchaseItemFlag>
        <specialOrderFlag>false</specialOrderFlag>
        <agreementId>2</agreementId>
        <description>System Support</description>
        <billedQuantity>1.00</billedQuantity>
        <uom>Month</uom>
        <extPrice>250.000000</extPrice>
        <extCost>0.000000</extCost>
        <sequenceNumber>2.00</sequenceNumber>
        <margin>250.000000</margin>
        <prorateCost>0.000000</prorateCost>
        <proratePrice>0.000000</proratePrice>
        <extendedProrateCost>0.000000</extendedProrateCost>
        <extendedProratePrice>0.000000</extendedProratePrice>
        <prorateCurrentPeriodFlag>false</prorateCurrentPeriodFlag>
        <agreementStatus>Active</agreementStatus>
      </agreementAddition>
      <agreementAddition>
        <id>4</id>
        <_info>
          <lastUpdated>2005-08-23T20:02:17Z</lastUpdated>
          <updatedBy>user10</updatedBy>
        </_info>
        <product>
          <id>746</id>
          <record>
            <id>746</id>
            <_info>
              <lastUpdated>2017-06-09T11:02:41Z</lastUpdated>
              <updatedBy>Admin1</updatedBy>
            </_info>
            <identifier>RB001</identifier>
            <description>Remote Backups</description>
            <inactiveFlag>false</inactiveFlag>
            <subcategory>
              <id>38</id>
              <name>Managed Services</name>
            </subcategory>
            <type>
              <id>33</id>
              <name>Fixed Cost Service</name>
            </type>
            <productClass>NonInventory</productClass>
            <serializedFlag>false</serializedFlag>
            <serializedCostFlag>false</serializedCostFlag>
            <phaseProductFlag>false</phaseProductFlag>
            <unitOfMeasure>
              <id>14</id>
              <name>Month</name>
            </unitOfMeasure>
            <minStockLevel>0</minStockLevel>
            <price>350.000000</price>
            <cost>100.000000</cost>
            <taxableFlag>true</taxableFlag>
            <customerDescription> Backup Plan

-- Seven Data Backups a Week
-- Send average of up to 1.2 GB daily
-- Store files for 90 days
-- Store up to 36GB total</customerDescription>
            <manufacturer>
              <id>13</id>
              <name>Microsoft</name>
            </manufacturer>
            <manufacturerPartNumber>1234567896</manufacturerPartNumber>
            <notes>Remote backups description</notes>
            <recurringFlag>false</recurringFlag>
            <recurringRevenue xsi:nil="true" />
            <recurringCost xsi:nil="true" />
            <recurringOneTimeFlag>false</recurringOneTimeFlag>
            <dateEntered>2014-10-22T08:48:08Z</dateEntered>
            <category>
              <id>18</id>
              <name>Managed Services</name>
            </category>
          </record>
          <identifier>RB001</identifier>
        </product>
        <quantity>1.00</quantity>
        <lessIncluded>0.00</lessIncluded>
        <unitPrice>350.000000</unitPrice>
        <unitCost xsi:nil="true" />
        <billCustomer>Billable</billCustomer>
        <effectiveDate>2005-08-01T00:00:00Z</effectiveDate>
        <cancelledDate xsi:nil="true" />
        <taxableFlag>false</taxableFlag>
        <invoiceDescription> Backup Plan

-- Seven Data Backups a Week
-- Send average of up to 1.2 GB daily
-- Store files for 90 days
-- Store up to 36GB total</invoiceDescription>
        <purchaseItemFlag>false</purchaseItemFlag>
        <specialOrderFlag>false</specialOrderFlag>
        <agreementId>2</agreementId>
        <description>Remote Backups</description>
        <billedQuantity>1.00</billedQuantity>
        <uom>Month</uom>
        <extPrice>350.000000</extPrice>
        <extCost>0.000000</extCost>
        <sequenceNumber>3.00</sequenceNumber>
        <margin>350.000000</margin>
        <prorateCost>0.000000</prorateCost>
        <proratePrice>0.000000</proratePrice>
        <extendedProrateCost>0.000000</extendedProrateCost>
        <extendedProratePrice>0.000000</extendedProratePrice>
        <prorateCurrentPeriodFlag>false</prorateCurrentPeriodFlag>
        <agreementStatus>Active</agreementStatus>
      </agreementAddition>
      <agreementAddition>
        <id>5</id>
        <_info>
          <lastUpdated>2005-09-13T15:26:08Z</lastUpdated>
          <updatedBy>User10</updatedBy>
        </_info>
        <product>
          <id>750</id>
          <record>
            <id>750</id>
            <_info>
              <lastUpdated>2019-04-23T10:12:32Z</lastUpdated>
              <updatedBy>Admin1</updatedBy>
            </_info>
            <identifier>SPAM -ConnectFilter</identifier>
            <description>SPAM -ConnectFilter</description>
            <inactiveFlag>false</inactiveFlag>
            <subcategory>
              <id>38</id>
              <name>Managed Services</name>
            </subcategory>
            <type>
              <id>33</id>
              <name>Fixed Cost Service</name>
            </type>
            <productClass>NonInventory</productClass>
            <serializedFlag>false</serializedFlag>
            <serializedCostFlag>false</serializedCostFlag>
            <phaseProductFlag>false</phaseProductFlag>
            <unitOfMeasure>
              <id>12</id>
              <name>User-based</name>
            </unitOfMeasure>
            <minStockLevel>0</minStockLevel>
            <price>30.000000</price>
            <cost>2.000000</cost>
            <taxableFlag>false</taxableFlag>
            <customerDescription>ConnectFilter (10 accounts) 
--Powerful Spam Filtering
         -  Heuristic-based content analysis providing over 95% accuracy
         -  End-user flexibility: users can customize own filters
         -  Quarantined messages are accessible via a web-based Message Center for review and disposition
--Real-Time Virus Protection
         -  All message parts are scanned for infected viruses, and infected messages are quarantined in the user's ConnectFilter Message Center for review and disposition
         -  Built-in protection from new techniques, including message fragments
         -  Industry leading McAfee AVERT provides dedicated connection to McAfee virus definition servers, protecting customers from new viruses</customerDescription>
            <recurringFlag>false</recurringFlag>
            <recurringRevenue xsi:nil="true" />
            <recurringCost xsi:nil="true" />
            <recurringOneTimeFlag>false</recurringOneTimeFlag>
            <dateEntered>2014-04-11T16:07:49Z</dateEntered>
            <category>
              <id>18</id>
              <name>Managed Services</name>
            </category>
          </record>
          <identifier>SPAM -ConnectFilter</identifier>
        </product>
        <quantity>1.00</quantity>
        <lessIncluded>0.00</lessIncluded>
        <unitPrice>30.000000</unitPrice>
        <unitCost xsi:nil="true" />
        <billCustomer>Billable</billCustomer>
        <effectiveDate>2005-09-01T00:00:00Z</effectiveDate>
        <cancelledDate xsi:nil="true" />
        <taxableFlag>false</taxableFlag>
        <invoiceDescription>ConnectFilter (10 accounts) 
--Powerful Spam Filtering
         -  Heuristic-based content analysis providing over 95% accuracy
         -  End-user flexibility: users can customize own filters
         -  Quarantined messages are accessible via a web-based Message Center for review and disposition
--Real-Time Virus Protection
         -  All message parts are scanned for infected viruses, and infected messages are quarantined in the user's ConnectFilter Message Center for review and disposition
         -  Built-in protection from new techniques, including message fragments
         -  Industry leading McAfee AVERT provides dedicated connection to McAfee virus definition servers, protecting customers from new viruses</invoiceDescription>
        <purchaseItemFlag>false</purchaseItemFlag>
        <specialOrderFlag>false</specialOrderFlag>
        <agreementId>2</agreementId>
        <description>SPAM -ConnectFilter</description>
        <billedQuantity>1.00</billedQuantity>
        <uom>User-based</uom>
        <extPrice>30.000000</extPrice>
        <extCost>0.000000</extCost>
        <sequenceNumber>4.00</sequenceNumber>
        <margin>30.000000</margin>
        <prorateCost>0.000000</prorateCost>
        <proratePrice>0.000000</proratePrice>
        <extendedProrateCost>0.000000</extendedProrateCost>
        <extendedProratePrice>0.000000</extendedProratePrice>
        <prorateCurrentPeriodFlag>false</prorateCurrentPeriodFlag>
        <agreementStatus>Active</agreementStatus>
      </agreementAddition>
      <agreementAddition>
        <id>10</id>
        <_info>
          <lastUpdated>2014-05-12T15:02:55Z</lastUpdated>
          <updatedBy>Admin1</updatedBy>
        </_info>
        <product>
          <id>749</id>
          <record>
            <id>749</id>
            <_info>
              <lastUpdated>2019-11-25T15:39:25Z</lastUpdated>
              <updatedBy>Admin1</updatedBy>
            </_info>
            <identifier>Block Time Renewal</identifier>
            <description>Block Time Renewal</description>
            <inactiveFlag>false</inactiveFlag>
            <subcategory>
              <id>43</id>
              <name>Block Time</name>
            </subcategory>
            <type>
              <id>32</id>
              <name>Miscellaneous</name>
            </type>
            <productClass>NonInventory</productClass>
            <serializedFlag>false</serializedFlag>
            <serializedCostFlag>false</serializedCostFlag>
            <phaseProductFlag>false</phaseProductFlag>
            <unitOfMeasure>
              <id>12</id>
              <name>User-based</name>
            </unitOfMeasure>
            <minStockLevel>0</minStockLevel>
            <price>0.000000</price>
            <cost>8.000000</cost>
            <taxableFlag>false</taxableFlag>
            <customerDescription>Block Time Renewal</customerDescription>
            <recurringFlag>false</recurringFlag>
            <recurringRevenue xsi:nil="true" />
            <recurringCost xsi:nil="true" />
            <recurringOneTimeFlag>false</recurringOneTimeFlag>
            <dateEntered>2005-06-02T14:43:59Z</dateEntered>
            <category>
              <id>21</id>
              <name>Block Time</name>
            </category>
          </record>
          <identifier>Block Time Renewal</identifier>
        </product>
        <quantity>8.00</quantity>
        <lessIncluded>1.00</lessIncluded>
        <unitPrice>10.000000</unitPrice>
        <unitCost>3.000000</unitCost>
        <billCustomer>Billable</billCustomer>
        <effectiveDate>2014-05-12T00:00:00Z</effectiveDate>
        <cancelledDate xsi:nil="true" />
        <taxableFlag>false</taxableFlag>
        <invoiceDescription>Block Time Renewal - how does this work?</invoiceDescription>
        <purchaseItemFlag>false</purchaseItemFlag>
        <specialOrderFlag>false</specialOrderFlag>
        <agreementId>2</agreementId>
        <description>Block Time Renewal</description>
        <billedQuantity>7.00</billedQuantity>
        <uom>User-based</uom>
        <extPrice>70.000000</extPrice>
        <extCost>24.000000</extCost>
        <sequenceNumber>5.00</sequenceNumber>
        <margin>46.000000</margin>
        <prorateCost>0.000000</prorateCost>
        <proratePrice>0.000000</proratePrice>
        <extendedProrateCost>0.000000</extendedProrateCost>
        <extendedProratePrice>0.000000</extendedProratePrice>
        <prorateCurrentPeriodFlag>false</prorateCurrentPeriodFlag>
        <agreementStatus>Active</agreementStatus>
      </agreementAddition>
    </agreementAdditions>
  </Agreement>
</Agreements>
```
