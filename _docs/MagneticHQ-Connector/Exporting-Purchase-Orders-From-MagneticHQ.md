---
slug: exporting-purchase-orders-from-magnetichq
redirect_from: "/article/exporting-purchase-orders-from-magnetichq"
title: Exporting Purchase Orders from Magnetic HQ
---
This task will export purchase orders from Magnetic HQ and store them in an XML file.

## Settings
### Connection
_Required_  
The MagneticHQ connection to use. See the [Connecting to MagentoHQ](connecting-to-magnetichq) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set this option to true to export all purchase orders, or set to false to download only new or modified purchase orders since this task last ran. Defaults to False.

### Status
_Required_
Select a status to filter the purchase orders on. Options are; 'Draft', 'Cancelled', 'Checked', 'Invoiced', Part_invoiced', 'Issued'.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. purchase_orders.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<MagneticHQData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Error />
  <PurchaseOrders>
    <PurchaseOrder>
      <Account>
        <Id>137623827</Id>
        <Version>0</Version>
        <Name>Test</Name>
        <RefCode>PO-0004</RefCode>
        <Status>DRAFT</Status>
        <Description />
        <PaymentTerms>30 Days</PaymentTerms>
        <Billed>0.0</Billed>
        <Tax>20.0</Tax>
        <Cost>10.0</Cost>
        <CurrencyCost>10.0</CurrencyCost>
        <Margin>0.0</Margin>
        <CurrencyMargin>0.0</CurrencyMargin>
        <TotalCost>12.0</TotalCost>
        <CurrencyTotalCost>12.0</CurrencyTotalCost>
        <CreatedDate>1501653600000</CreatedDate>
        <IssuedDate>0</IssuedDate>
        <Company>
          <Id>136271987</Id>
          <Version>1</Version>
          <Name>TestCompany</Name>
          <ContactPerson />
          <BillingName />
          <ContactNumber />
          <EmailAddress />
          <PhysicalAddress />
          <PostalAddress />
          <Website />
          <MailDomain />
          <Description />
          <CreatedDate>1500384746834</CreatedDate>
          <OtherInfo />
          <ExternalReference />
          <Tag />
          <TaxNumber />
          <KeyPerson>
            <Id>137623819</Id>
            <Version>1</Version>
            <Title />
            <FirstName>ContactNameTest</FirstName>
            <LastName />
            <FullName>ContactNameTest </FullName>
            <LandNumber />
            <CellNumber />
            <FaxNumber />
            <Email />
            <PhysicalAddress />
            <PostalAddress />
            <Position />
            <OtherInfo />
            <ExternalReference />
            <Tag />
            <CreatedDate>1501688201524</CreatedDate>
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
          <ApprovedAccountsCustomer>false</ApprovedAccountsCustomer>
          <ApprovedAccountsSupplier>false</ApprovedAccountsSupplier>
          <LastActivityDate>1501688201603</LastActivityDate>
          <CustomFields>
            <item>
              <key>53134950</key>
              <value />
            </item>
            <item>
              <key>74751737</key>
              <value />
            </item>
            <item>
              <key>53179986</key>
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
              <value>1</value>
            </item>
            <item>
              <key>54068158</key>
              <value />
            </item>
          </CustomFields>
          <ModifiedDate>1501688201603</ModifiedDate>
        </Company>
        <DeliveryAddress />
        <Contact>
          <Id>137623819</Id>
          <Version>1</Version>
          <Title />
          <FirstName>ContactNameTest</FirstName>
          <LastName />
          <FullName>ContactNameTest </FullName>
          <LandNumber />
          <CellNumber />
          <FaxNumber />
          <Email />
          <PhysicalAddress />
          <PostalAddress />
          <Position />
          <OtherInfo />
          <ExternalReference />
          <Tag />
          <CreatedDate>1501688201524</CreatedDate>
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
          <CustomFields />
        </Contact>
        <Grouping>
          <Id>137623824</Id>
          <Version>0</Version>
          <Code>1123</Code>
          <Name>ProjectNameTest</Name>
          <Extra />
          <Access>PUBLIC</Access>
          <CreatedDate>1501688201618</CreatedDate>
          <CustomFields />
          <ModifiedDate>1501688201624</ModifiedDate>
          <SignedDate>0</SignedDate>
          <StartDate>0</StartDate>
          <EndDate>0</EndDate>
          <ExternalReference />
          <Signed>true</Signed>
          <Status />
          <Amount>0.0</Amount>
          <MonthlyAmount>0.0</MonthlyAmount>
          <PercentageComplete>0</PercentageComplete>
          <Complete>false</Complete>
          <Archive>false</Archive>
          <Tag />
          <TaskStatuses />
          <ContactCompany>
            <Id>136271987</Id>
            <Version>1</Version>
            <Name>TestCompany</Name>
            <ContactPerson />
            <BillingName />
            <ContactNumber />
            <EmailAddress />
            <PhysicalAddress />
            <PostalAddress />
            <Website />
            <MailDomain />
            <Description />
            <CreatedDate>1500384746834</CreatedDate>
            <OtherInfo />
            <ExternalReference />
            <Tag />
            <TaxNumber />
            <KeyPerson>
              <Id>137623819</Id>
              <Version>1</Version>
              <Title />
              <FirstName>ContactNameTest</FirstName>
              <LastName />
              <FullName>ContactNameTest </FullName>
              <LandNumber />
              <CellNumber />
              <FaxNumber />
              <Email />
              <PhysicalAddress />
              <PostalAddress />
              <Position />
              <OtherInfo />
              <ExternalReference />
              <Tag />
              <CreatedDate>1501688201524</CreatedDate>
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
            <ApprovedAccountsCustomer>false</ApprovedAccountsCustomer>
            <ApprovedAccountsSupplier>false</ApprovedAccountsSupplier>
            <LastActivityDate>1501688201603</LastActivityDate>
            <CustomFields>
              <item>
                <key>53134950</key>
                <value />
              </item>
              <item>
                <key>74751737</key>
                <value />
              </item>
              <item>
                <key>53179986</key>
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
                <value>1</value>
              </item>
              <item>
                <key>54068158</key>
                <value />
              </item>
            </CustomFields>
            <ModifiedDate>1501688201603</ModifiedDate>
          </ContactCompany>
          <Contact>
            <Id>137623819</Id>
            <Version>1</Version>
            <Title />
            <FirstName>ContactNameTest</FirstName>
            <LastName />
            <FullName>ContactNameTest</FullName>
            <LandNumber />
            <CellNumber />
            <FaxNumber />
            <Email />
            <PhysicalAddress />
            <PostalAddress />
            <Position />
            <OtherInfo />
            <ExternalReference />
            <Tag />
            <CreatedDate>1501688201524</CreatedDate>
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
            <CustomFields />
          </Contact>
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
          <Author>
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
          </Author>
          <Winner>
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
          </Winner>
          <DefaultBillable>NOTSET</DefaultBillable>
          <TimeWarning>NONE</TimeWarning>
          <GrossProfitFinancialWarning>NONE</GrossProfitFinancialWarning>
          <NetProfitFinancialWarning>NONE</NetProfitFinancialWarning>
          <Duration>0</Duration>
        </Grouping>
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
        <Discount>0.0</Discount>
        <Archive>false</Archive>
        <Tag />
        <HideQtyAndCost>false</HideQtyAndCost>
        <ModifiedDate>1501688201645</ModifiedDate>
        <Currency>GBP</Currency>
        <ExchangeRate>1.0</ExchangeRate>
      </Account>
      <LineItems>
        <LineItem>
          <Id>137623829</Id>
          <Version>0</Version>
          <ItemType>
            <Id>74761164</Id>
            <Version>0</Version>
            <Name>Carriage</Name>
            <ExternalName />
            <Cost>10.0</Cost>
            <TaxType>TAX</TaxType>
            <Markup>999.0</Markup>
            <Description />
            <Company>
              <Id>53090725</Id>
              <Version>13</Version>
              <Name>Company Ltd</Name>
              <ContactPerson>Customer</ContactPerson>
              <ContactNumber>07123456789</ContactNumber>
              <EmailAddress>magnetic@email.co.uk</EmailAddress>
              <PhysicalAddress />
              <PostalAddress />
              <Website />
              <MailDomain />
              <DefaultSkin />
              <GroupingName>Project</GroupingName>
              <TotalSmsesSent>0</TotalSmsesSent>
              <TotalEmailsSent>0</TotalEmailsSent>
              <CreatedDate>1446813531845</CreatedDate>
              <Active>true</Active>
              <ReceiveEmailNotifications>true</ReceiveEmailNotifications>
              <Hr>true</Hr>
              <GroupingCodePrefix />
              <AccountsPrefix />
              <NotificationsActive>BOTH</NotificationsActive>
              <NotifyMethod>EMAIL</NotifyMethod>
              <RetentionPeriod>90</RetentionPeriod>
              <SignatureRecognition>UPDATECONTACTS</SignatureRecognition>
              <Accounts>true</Accounts>
              <Ical>true</Ical>
              <PricingPackage>FREE</PricingPackage>
              <CloseDate>1447970400000</CloseDate>
              <OnlyApprovedCompaniesInAccounts>false</OnlyApprovedCompaniesInAccounts>
              <UserRate>250.0</UserRate>
              <FreelancerRate>0.0</FreelancerRate>
              <FixedRate>0.0</FixedRate>
              <MaxMonthlyActiveUsers>8</MaxMonthlyActiveUsers>
              <MaxMonthlyActiveUserList>gtdemo@flowbird.co.uk,junior@creativenet.net,l@magneticdemo.net,copywriter@magnetichq.com,designer@magneticdemo.net,creative@magneticdemo.net,magnetic@flowbird.co.uk</MaxMonthlyActiveUserList>
              <MaxMonthlyActiveFreelancers>0</MaxMonthlyActiveFreelancers>
              <MaxMonthlyActiveFreelancerList />
              <GroupingCode>3486</GroupingCode>
              <TaxFree>false</TaxFree>
              <Country>GB</Country>
              <TaskItemTypeRequired>true</TaskItemTypeRequired>
              <BlockAccessTimesheetsNotFilled>true</BlockAccessTimesheetsNotFilled>
              <RecurringTasksEnabled>true</RecurringTasksEnabled>
              <PaymentTerms>30 Days,30 Days from Invoice,14 Days from Invoice,7 Days from Invoice,30 Days from Statement,50% deposit + Progress Payments,50% deposit + 50% on completion,60% deposit,66% deposit,75% deposit,Cash On Delivery,On Invoice,On Signing,Paid</PaymentTerms>
              <NoCostEstimateSendingDraft>false</NoCostEstimateSendingDraft>
              <TaxPercentage>20.0</TaxPercentage>
              <OpportunitiesBillable>NOTSET</OpportunitiesBillable>
              <AccountsFooterText />
              <GroupAccountLineItems>false</GroupAccountLineItems>
              <AccountIntegrationType>NONE</AccountIntegrationType>
              <CostEstimatesIntegrationType>NONE</CostEstimatesIntegrationType>
              <PurchaseOrdersIntegrationType>NONE</PurchaseOrdersIntegrationType>
              <RevenueIntegrationType>NONE</RevenueIntegrationType>
              <BaseCurrency>GBP</BaseCurrency>
              <OnlyCreateAccountsOffCostEstimate>false</OnlyCreateAccountsOffCostEstimate>
              <BudgetWarningLevel>0.75</BudgetWarningLevel>
            </Company>
            <BillableByDefault>false</BillableByDefault>
            <Archive>false</Archive>
            <ArchivedDate>0</ArchivedDate>
            <CreatedDate>1463648972986</CreatedDate>
          </ItemType>
          <RefCode>137623824</RefCode>
          <Unit>1.0</Unit>
          <Cost>10.0</Cost>
          <Markup>0.0</Markup>
          <Ordering>0</Ordering>
          <TaxType>TAX</TaxType>
          <Notes />
          <DocType>PURCHASE_ORDER</DocType>
        </LineItem>
      </LineItems>
    </PurchaseOrder>
    </PurchaseOrders>
    </MagneticHQData>
```
