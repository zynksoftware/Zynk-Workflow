---
slug: exporting-records-from-zoho-crm-v2
title: Exporting Records from Zoho CRM
---
This task will export records from various modules from your Zoho CRM account. The results will be output in XML format.

## Settings
### Connection
_Required_  
The Zoho CRM Connection to use for exporting records.  See the [Connecting to Zoho CRM](connecting-to-zoho-crm-v2) article if you require more information on how to create/manage connections.

### Export All
_Required_  
Set to true to export all records, or set to false to export only new records or ones that have been modified since the date shown in the Export From setting.

### Export From
_Required_  
The date to download new and modified records from, when the task is not set to export all. This will update automatically when the task runs.

### Export Subform Records
_Required_  
Set to true if the module you are exporting from contains one or more subforms that you would like to export records from.

### Filter
_Optional_  
Specify criteria to use to filter the records. See below for a sample filter. Note that you can only specify a maximum of 10 conditions in the filter. Special characters such as parentheses and commas must be escaped using a back slash when used as a value.

`(((Last_Name:equals:Steve) and (Company:starts_with:Zynk)) or (Lead_Status:equals:Contacted))`

### Module Name
_Required_  
Enter the name of the module to export records from. A list of the possible module names is provided below. Custom modules can also be used, but are not listed below.

 * accounts
 * activities
 * calls
 * campaigns
 * cases
 * contacts
 * deals
 * events
 * invoices
 * leads
 * notes
 * pricebooks
 * products
 * purchaseorders
 * quotes
 * salesorders
 * solutions
 * tasks
 * vendors

### Output File
_Required_  
Specify the XML file to export the records to.

### Page Size
_Required_  
The number of records to include in each batch requested by Zynk. The maximum value is 200.

### Related Records
_Optional_  
Where Zoho returns the ID of a related record, this setting can be used to include these records in the export. 

For example, when exporting contacts, Zoho returns an `Account_Name` object, with the `name` and `id` of the account the contact is associated with. Using these settings, you can export full details of this account.

 * __Module Name__ - Enter the name of the related module you want to export records from. See the Module Name setting above for a list of valid module names. Using the above example, this would be 'accounts'.
 * __Path__ - Enter the path Zynk should follow when searching for the ID of the related record. This should consist of the object or field names separated by forward slashes. Using the above example, this would be 'Account_Name/id'.

The related record will be written to the output file following the ID node that was specified in the Path setting. It will be written as an object, with the name `Related_{module name}`. Using the above example, the name would be `Related_accounts`.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file, when the Module Name setting is set to 'contacts':

```xml
<?xml version="1.0" encoding="utf-8"?>
<Records Module="contacts">
  <Record>
    <ExternalId>FRED001</ExternalId>
    <Object Name="Owner">
      <Field Name="name">adam.wardle</Field>
      <Field Name="id">919325000000064001</Field>
      <Errors />
    </Object>
    <Field Name="Email">fred.white@example.com</Field>
    <Field Name="Description" />
    <Field Name="$currency_symbol">£</Field>
    <Field Name="Mailing_Zip">AB12CD</Field>
    <Field Name="Reports_To" />
    <Field Name="Other_Phone" />
    <Field Name="Mailing_State">A state</Field>
    <Field Name="Twitter" />
    <Field Name="Other_Zip" />
    <Field Name="Mailing_Street">A street</Field>
    <Field Name="Other_State" />
    <Field Name="Salutation">Mr</Field>
    <Field Name="Other_Country" />
    <Field Name="Last_Activity_Time">2019-06-19T11:24:07</Field>
    <Field Name="First_Name">Fred</Field>
    <Field Name="Full_Name">Mr Fred White</Field>
    <Field Name="Asst_Phone" />
    <Field Name="Record_Image" />
    <Field Name="Department" />
    <Object Name="Modified_By">
      <Field Name="name">adam.wardle</Field>
      <Field Name="id">919325000000064001</Field>
      <Errors />
    </Object>
    <Field Name="Skype_ID" />
    <Field Name="Add_to_QuickBooks">False</Field>
    <Field Name="$process_flow">False</Field>
    <Field Name="Assistant">John</Field>
    <Field Name="Phone">999999999</Field>
    <Field Name="Mailing_Country">GB</Field>
    <Object Name="Account_Name">
      <Field Name="name">Test Account</Field>
      <Field Name="id">919325000000064034</Field>
    </Object>
    <Field Name="id">919325000000091003</Field>
    <Field Name="Email_Opt_Out">True</Field>
    <Field Name="$approved">True</Field>
    <Field Name="Reporting_To" />
    <Object Name="$approval">
      <Field Name="delegate">False</Field>
      <Field Name="approve">False</Field>
      <Field Name="reject">False</Field>
      <Field Name="resubmit">False</Field>
      <Errors />
    </Object>
    <Field Name="Modified_Time">2019-06-19T11:24:07</Field>
    <Field Name="Date_of_Birth">2000-01-01</Field>
    <Field Name="Mailing_City">A city</Field>
    <Field Name="Other_City" />
    <Field Name="Created_Time">2015-04-10T12:54:57</Field>
    <Field Name="Title" />
    <Field Name="$editable">True</Field>
    <Field Name="Other_Street" />
    <Field Name="Mobile">99989989</Field>
    <Field Name="Home_Phone" />
    <Field Name="Last_Name">White</Field>
    <Field Name="Lead_Source" />
    <Object Name="Created_By">
      <Field Name="name">adam.wardle</Field>
      <Field Name="id">919325000000064001</Field>
      <Errors />
    </Object>
    <Field Name="Fax">99999999</Field>
    <Field Name="Secondary_Email" />
    <Errors />
  </Record>
</Records>
```