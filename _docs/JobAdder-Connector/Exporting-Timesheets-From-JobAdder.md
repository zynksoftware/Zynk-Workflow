---
slug: exporting-timesheets-from-jobadder
title: Exporting Timesheets from JobAdder
---
This task will export timesheets from JobAdder in the XML format. See below for a sample output file.

## Settings
### Connection
_Required_  
The JobAdder connection to use. See the [Connecting to JobAdder](connecting-to-jobadder) article if you require more information on how to create/manage connections.

### Status
_Required_  
The status to export timesheets at. E.g. Approved.

### Timesheets From
_Required_  
Rolling date to export timesheets from. Timesheets from this date until the current time minus 1 day will be exported as it is not possible to track modifications via the JobAdder API.

### Output File
_Required_  
The name of the file to export the timesheets to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Timesheets xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Timesheet>
    <Period>
      <Start>2018-07-23T00:00:00</Start>
      <End>2018-07-29T00:00:00</End>
    </Period>
    <CreatedAt>2018-07-27T05:18:20</CreatedAt>
    <SubmittedAt>2018-07-27T05:18:20</SubmittedAt>
    <ApprovedAt>2018-07-27T05:19:18</ApprovedAt>
    <ApprovedBy>
      <UserId xsi:nil="true" />
      <FirstName>Andrew</FirstName>
      <LastName>Gittus</LastName>
      <Email>support@zynk.com</Email>
      <Inactive xsi:nil="true" />
      <Deleted xsi:nil="true" />
    </ApprovedBy>
    <Entries>
      <TimesheetEntry>
        <Date>2018-07-26T00:00:00</Date>
        <Type>Days</Type>
      </TimesheetEntry>
      <TimesheetEntry>
        <Date>2018-07-27T00:00:00</Date>
        <Type>Days</Type>
      </TimesheetEntry>
    </Entries>
    <Placement>
      <PlacementId>84046</PlacementId>
      <JobTitle>Zynk Developer Test Job</JobTitle>
      <Job>
        <JobId>281609</JobId>
        <JobTitle>Zynk Developer Test Job</JobTitle>
      </Job>
      <Candidate>
        <CandidateId>3225867</CandidateId>
        <FirstName>Andrew</FirstName>
        <LastName>Gittus</LastName>
        <Email>support@zynk.com</Email>
        <Status>
          <StatusId>14462</StatusId>
          <Name>Active</Name>
          <Active>true</Active>
          <Default>true</Default>
        </Status>
        <SeekingUpdatedAt>0001-01-01T00:00:00</SeekingUpdatedAt>
      </Candidate>
      <Approved>true</Approved>
      <ApprovedAt>2018-07-27T01:15:42</ApprovedAt>
      <Type>Contract</Type>
      <Status>
        <StatusId>928</StatusId>
        <Name>Active Placement</Name>
        <Active>true</Active>
        <Default>true</Default>
      </Status>
      <StartDate>2018-07-26T00:00:00</StartDate>
      <EndDate>2018-08-01T00:00:00</EndDate>
      <Company>
        <CompanyId>398155</CompanyId>
        <Name>Zynk Test Company</Name>
        <PrimaryAddress>
          <Street>
            <string>i6 Charlotte Square</string>
            <string>6-8 Charlotte Square</string>
          </Street>
          <City>Newcastle upon Tyne</City>
          <State>Tyne &amp; Wear</State>
          <PostalCode>NE1 4X</PostalCode>
          <Country>United Kingdom</Country>
          <Postcode>NE1 4X</Postcode>
        </PrimaryAddress>
        <CustomFields>
          <CustomField>
            <FieldId>1</FieldId>
            <Name>Sage50 A/C #</Name>
            <Type>Text</Type>
            <Value>ZYNK0001</Value>
          </CustomField>
        </CustomFields>
        <Status>
          <StatusId>10518</StatusId>
          <Name>Internal client</Name>
          <Active>true</Active>
          <Default>true</Default>
        </Status>
        <Owner>
          <UserId>213554</UserId>
          <FirstName>Andrew</FirstName>
          <LastName>Gittus</LastName>
          <Email>support@zynk.com</Email>
          <Inactive xsi:nil="true" />
          <Deleted xsi:nil="true" />
        </Owner>
      </Company>
      <Contact>
        <ContactId>3225866</ContactId>
        <FirstName>Andrew</FirstName>
        <LastName>Gittus</LastName>
        <Email>support@zynk.com</Email>
      </Contact>
      <WorkplaceAddress>
        <Street>
          <string>i6 Charlotte Square</string>
          <string>6-8 Charlotte Square</string>
        </Street>
        <City>Newcastle upon Tyne</City>
        <State>Tyne &amp; Wear</State>
        <PostalCode>NE1 4X</PostalCode>
        <Country>United Kingdom</Country>
        <Postcode>NE1 4X</Postcode>
      </WorkplaceAddress>
       <ContractRate>
        <RatePer>Day</RatePer>
        <HoursPerWeek>0</HoursPerWeek>
        <ClientRate>99.00</ClientRate>
        <CandidateRate>62.00</CandidateRate>
        <OnCostsType>Percent</OnCostsType>
        <NetMargin>30.80</NetMargin>
      </ContractRate>
      <BillingAddress>
        <Contact>
          <ContactId>3225866</ContactId>
          <FirstName>Andrew</FirstName>
          <LastName>Gittus</LastName>
          <Email>support@zynk.com</Email>
        </Contact>
        <Address>
          <Street>
            <string>i6 Charlotte Square</string>
            <string>6-8 Charlotte Square</string>
          </Street>
          <City>Newcastle upon Tyne</City>
          <State>Tyne &amp; Wear</State>
          <PostalCode>NE1 4X</PostalCode>
          <Country>United Kingdom</Country>
          <Postcode>NE1 4X</Postcode>
        </Address>
        <Email>support@zynk.com</Email>
        <OrderRef>12345678</OrderRef>
        <InvoiceRef>12345678</InvoiceRef>
        <Terms>30 Days</Terms>
        <DueDate>2018-05-31T00:00:00</DueDate>
      </BillingAddress>
      <CreatedBy>
        <UserId>213554</UserId>
        <FirstName>Andrew</FirstName>
        <LastName>Gittus</LastName>
        <Email>support@zynk.com</Email>
        <Inactive xsi:nil="true" />
        <Deleted xsi:nil="true" />
      </CreatedBy>
      <CreatedAt>2018-07-27T01:15:42</CreatedAt>
      <UpdatedBy>
        <UserId>213554</UserId>
        <FirstName>Andrew</FirstName>
        <LastName>Gittus</LastName>
        <Email>support@zynk.com</Email>
        <Inactive xsi:nil="true" />
        <Deleted xsi:nil="true" />
      </UpdatedBy>
      <UpdatedAt>2018-07-27T01:16:01</UpdatedAt>
      <CustomFields>
        <CustomField>
          <FieldId>1</FieldId>
          <Name>Sage Individual Invoice</Name>
          <Type>List</Type>
          <Value>Yes</Value>
        </CustomField>
      </CustomFields>
    </Placement>
  </Timesheet>
```