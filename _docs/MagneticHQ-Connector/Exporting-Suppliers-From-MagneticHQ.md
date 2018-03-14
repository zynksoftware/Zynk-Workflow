---
slug: exporting-suppliers-from-magnetichq
redirect_from: "/article/exporting-suppliers-from-magnetichq"
title: Exporting Suppliers from Magnetic HQ
---
This task will export suppliers from Magnetic HQ and store them in an XML file.

## Settings
### Connection
_Required_  
The MagneticHQ connection to use. See the [Connecting to MagentoHQ](connecting-to-magnetichq) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set this option to true to export all customers, or set to false to download only new or modified customers since this task last ran. Defaults to False.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. suppliers.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<MagneticHQData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Error />
  <Suppliers>
    <Supplier>
      <Id>53096646</Id>
      <Version>4</Version>
      <Name>Supplier Company Ltd</Name>
      <ContactPerson>Nathan Hopkins</ContactPerson>
      <BillingName />
      <ContactNumber />
      <EmailAddress>Nathan.Hopkins@email.com</EmailAddress>
      <PhysicalAddress />
      <PostalAddress />
      <Website />
      <MailDomain />
      <Description />
      <CreatedDate>1446814347791</CreatedDate>
      <OtherInfo>Machining</OtherInfo>
      <ExternalReference />
      <Tag>supplier</Tag>
      <TaxNumber />
      <KeyPerson>
        <Id>53096650</Id>
        <Version>1</Version>
        <Title>Mr</Title>
        <FirstName>Nathan</FirstName>
        <LastName>Hopkins</LastName>
        <FullName>Nathan Hopkins</FullName>
        <LandNumber />
        <CellNumber />
        <FaxNumber />
        <Email>nathan.hopkinsn@email.com</Email>
        <PhysicalAddress />
        <PostalAddress />
        <Position />
        <OtherInfo>Machining</OtherInfo>
        <ExternalReference />
        <Tag />
        <CreatedDate>1446814347823</CreatedDate>
        <Owner>
          <Id>53090727</Id>
          <Version>194</Version>
          <Title>Studio Manager</Title>
          <FirstName>Oliver</FirstName>
          <LastName>Jeffery</LastName>
          <FullName>Oliver Jeffery</FullName>
          <Email>magnetic@email.co.uk</Email>
          <ContactNumber>07123456789</ContactNumber>
          <Description />
          <UserName>magnetic@email.co.uk</UserName>
          <RoleType>ADMIN</RoleType>
          <UserManager>true</UserManager>
          <Skin>bing</Skin>
          <Accounts>true</Accounts>
          <Grouping>Design</Grouping>
          <CreatedDate>1446813531845</CreatedDate>
          <LastAccessedDate>1500891379782</LastAccessedDate>
          <LoginAttempts>0</LoginAttempts>
          <TimeTrackingUser>false</TimeTrackingUser>
          <NoWorkDone>1446731581084</NoWorkDone>
          <PageSize>40</PageSize>
          <Status>ACTIVATED</Status>
          <AccountsAdministrator>true</AccountsAdministrator>
          <AddGroupings>true</AddGroupings>
          <NotifyMethod>EMAIL</NotifyMethod>
          <HrManager>true</HrManager>
          <TimeZone>36,GMT+02:00</TimeZone>
          <ReceiveDailyNotification>false</ReceiveDailyNotification>
          <ReceiveRealtimeNotifications>true</ReceiveRealtimeNotifications>
          <HideDetails>false</HideDetails>
          <TaskView>LIST</TaskView>
          <GroupingSignedView>STATUSLANE</GroupingSignedView>
          <GroupingUnsignedView>LIST</GroupingUnsignedView>
          <Type>SALES</Type>
          <RewardStatus>NONE</RewardStatus>
          <AnnualLeave>26</AnnualLeave>
          <SickLeave>0</SickLeave>
          <CompassionateLeave>0</CompassionateLeave>
          <OtherLeave>0</OtherLeave>
          <ReceiveHrEmails>true</ReceiveHrEmails>
          <HourCapacityPerDay>8.0</HourCapacityPerDay>
          <EmployeeCost>0.0</EmployeeCost>
          <CostEstimatePermission>WRITE_APPROVE</CostEstimatePermission>
          <PurchaseOrderPermission>WRITE</PurchaseOrderPermission>
          <TaxInvoicePermission>WRITE</TaxInvoicePermission>
          <SupplierInvoicePermission>WRITE</SupplierInvoicePermission>
          <ExpensePermission>NONE</ExpensePermission>
          <Active>true</Active>
          <FirstLastInitial>Oliver J</FirstLastInitial>
        </Owner>
        <Global>true</Global>
        <CustomFields />
      </KeyPerson>
      <Owner>
        <Id>53090727</Id>
        <Version>194</Version>
        <Title>Studio Manager</Title>
        <FirstName>Oliver</FirstName>
        <LastName>Jeffery</LastName>
        <FullName>Oliver Jeffery</FullName>
        <Email>magnetic@email.co.uk</Email>
        <ContactNumber>07123456789</ContactNumber>
        <Description />
        <UserName>magnetic@email.co.uk</UserName>
        <RoleType>ADMIN</RoleType>
        <UserManager>true</UserManager>
        <Skin>bing</Skin>
        <Accounts>true</Accounts>
        <Grouping>Design</Grouping>
        <CreatedDate>1446813531845</CreatedDate>
        <LastAccessedDate>1500891379782</LastAccessedDate>
        <LoginAttempts>0</LoginAttempts>
        <TimeTrackingUser>false</TimeTrackingUser>
        <NoWorkDone>1446731581084</NoWorkDone>
        <PageSize>40</PageSize>
        <Status>ACTIVATED</Status>
        <AccountsAdministrator>true</AccountsAdministrator>
        <AddGroupings>true</AddGroupings>
        <NotifyMethod>EMAIL</NotifyMethod>
        <HrManager>true</HrManager>
        <TimeZone>36,GMT+02:00</TimeZone>
        <ReceiveDailyNotification>false</ReceiveDailyNotification>
        <ReceiveRealtimeNotifications>true</ReceiveRealtimeNotifications>
        <HideDetails>false</HideDetails>
        <TaskView>LIST</TaskView>
        <GroupingSignedView>STATUSLANE</GroupingSignedView>
        <GroupingUnsignedView>LIST</GroupingUnsignedView>
        <Type>SALES</Type>
        <RewardStatus>NONE</RewardStatus>
        <AnnualLeave>26</AnnualLeave>
        <SickLeave>0</SickLeave>
        <CompassionateLeave>0</CompassionateLeave>
        <OtherLeave>0</OtherLeave>
        <ReceiveHrEmails>true</ReceiveHrEmails>
        <HourCapacityPerDay>8.0</HourCapacityPerDay>
        <EmployeeCost>0.0</EmployeeCost>
        <CostEstimatePermission>WRITE_APPROVE</CostEstimatePermission>
        <PurchaseOrderPermission>WRITE</PurchaseOrderPermission>
        <TaxInvoicePermission>WRITE</TaxInvoicePermission>
        <SupplierInvoicePermission>WRITE</SupplierInvoicePermission>
        <ExpensePermission>NONE</ExpensePermission>
        <Active>true</Active>
        <FirstLastInitial>Oliver J</FirstLastInitial>
      </Owner>
      <Global>true</Global>
      <ApprovedAccountsCustomer>true</ApprovedAccountsCustomer>
      <ApprovedAccountsSupplier>true</ApprovedAccountsSupplier>
      <LastActivityDate>1500389298586</LastActivityDate>
      <CustomFields>
        <item>
          <key>53179986</key>
          <value>Machining</value>
        </item>
      </CustomFields>
      <ModifiedDate>1500389298586</ModifiedDate>
    </Supplier>
    </Suppliers>
    </MagneticHQData>
```
