---
slug: exporting-customers-from-magnetichq
redirect_from: "/article/exporting-customers-from-magnetichq"
title: Exporting Customers from Magnetic HQ
---
This task will export customers from Magnetic HQ and store them in an XML file.

## Settings
### Connection
_Required_  
The MagneticHQ connection to use. See the [Connecting to MagentoHQ](connecting-to-magnetichq) if you require more information on how to create/manage connections.

### Download All
_Required_  
Set this option to true to export all customers, or set to false to download only new or modified customers since this task last ran. Defaults to False.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. customers.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<MagneticHQData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>53093039</Id>
      <Version>2</Version>
      <Name>Zynk</Name>
      <ContactPerson>Nathan</ContactPerson>
      <BillingName />
      <ContactNumber />
      <EmailAddress>Nathan@Zynk.com</EmailAddress>
      <PhysicalAddress />
      <PostalAddress />
      <Website />
      <MailDomain>Zynk.com</MailDomain>
      <Description />
      <CreatedDate>1446814277684</CreatedDate>
      <OtherInfo>Dormant Company</OtherInfo>
      <ExternalReference />
      <Tag>customer</Tag>
      <TaxNumber />
      <KeyPerson>
        <Id>63775864</Id>
        <Version>1</Version>
        <Title />
        <FirstName>Nathan</FirstName>
        <LastName>Hopkins</LastName>
        <FullName>Nathan Hopkins</FullName>
        <LandNumber />
        <CellNumber />
        <FaxNumber />
        <Email />
        <PhysicalAddress />
        <PostalAddress />
        <Position />
        <OtherInfo />
        <ExternalReference>Created from a key person.</ExternalReference>
        <Tag />
        <CreatedDate>1457410780016</CreatedDate>
        <Owner>
          <Id>53090727</Id>
          <Version>202</Version>
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
          <LastAccessedDate>1503566378222</LastAccessedDate>
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
        <Global>false</Global>
        <CustomFields />
      </KeyPerson>
      <Owner>
        <Id>53090727</Id>
        <Version>202</Version>
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
        <LastAccessedDate>1503566378222</LastAccessedDate>
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
      <ApprovedAccountsSupplier>false</ApprovedAccountsSupplier>
      <LastActivityDate>0</LastActivityDate>
      <CustomFields>
        <item>
          <key>53134950</key>
          <value />
        </item>
        <item>
          <key>53130884</key>
          <value />
        </item>
        <item>
          <key>53164750</key>
          <value />
        </item>
        <item>
          <key>53164698</key>
          <value>0</value>
        </item>
      </CustomFields>
      <ModifiedDate>1446814277684</ModifiedDate>
    </Customer>
    </Customers>
    </MagneticHQData>
```
