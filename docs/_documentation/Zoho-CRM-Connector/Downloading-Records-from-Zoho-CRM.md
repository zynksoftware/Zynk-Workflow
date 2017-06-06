---
slug: downloading-records-from-zoho-crm
redirect_from: "/article/364-downloading-records-from-zoho-crm"
title: Downloading Records from Zoho CRM
---
This task will download various types of records from your Zoho CRM account, in XML format.

## Settings
### Connection
_Required_  
The Zoho CRM Connection to use for deleting records.  See the [Connecting to Zoho CRM](connecting-to-zoho-crm) article if you require more information on how to create/manage connections.

### Download All
_Required_  
Set to true to download all records, or set to false to download only new records or ones that have been modified since the last time you ran the task.

### Filter
_Optional_  
Specify criteria to use to filter the records. See below for a sample filter. Note that you can only specify a maximum of 5 conditions in the filter.  `(((Last Name:Steve) AND (Company:Zynk)) OR (Lead Status:Contacted))`

### Output File
_Required_  
Specify the XML file to download the records to.

### Record Type
_Required_  
The type of record to be deleted. The available options are:	

 * Accounts
 * Calls
 * Campaigns
 * Contacts
 * Events
 * Invoices
 * Leads
 * Potentials
 * Price Books
 * Products
 * Purchase Orders
 * Quotes
 * Sales Orders
 * Solutions
 * Tasks
 * Vendors

### Related Records
_Optional_  
Enter a list of Zoho module names to download related records from. For example, if the 'Record Type' setting is set to 'Sales Orders' and you enter 'Accounts' into the related records list, the task will automatically download details of the account associated with each sales order.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file, when the Record Type setting is set to 'Accounts':

```xml
<?xml version="1.0" encoding="utf-8"?>
<Accounts>
    <row no="1">
        <FL val="ACCOUNTID">919325000000064034</FL>
        <FL val="SMOWNERID">919325000000064001</FL>
        <FL val="Account Owner">
            <![CDATA[adam.wardle]]>
        </FL>
        <FL val="Account Name">
            <![CDATA[Test Account]]>
        </FL>
        <FL val="Account Number">
            <![CDATA[0]]>
        </FL>
        <FL val="Employees">
            <![CDATA[0]]>
        </FL>
        <FL val="Annual Revenue">
            <![CDATA[0]]>
        </FL>
        <FL val="SIC Code">
            <![CDATA[0]]>
        </FL>
        <FL val="SMCREATORID">919325000000064001</FL>
        <FL val="Created By">
            <![CDATA[adam.wardle]]>
        </FL>
        <FL val="MODIFIEDBY">919325000000064001</FL>
        <FL val="Modified By">
            <![CDATA[adam.wardle]]>
        </FL>
        <FL val="Created Time">
            <![CDATA[2013-07-26 02:57:22]]>
        </FL>
        <FL val="Modified Time">
            <![CDATA[2013-07-26 04:22:10]]>
        </FL>
        <FL val="Billing Street">
            <![CDATA[test]]>
        </FL>
        <FL val="Billing State">
            <![CDATA[test]]>
        </FL>
        <FL val="Last Activity Time">
            <![CDATA[2013-07-26 04:22:10]]>
        </FL>
    </row>
</Accounts>
```

Sample output file, when the Record Type setting is set to 'SalesOrders':

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<SalesOrders>
    <row no="1">
        <FL val="SALESORDERID">639175000000054025</FL>
        <FL val="SO Number">
            <![CDATA[639175000000054027]]>
        </FL>
        <FL val="Subject">
            <![CDATA[test sales order]]>
        </FL>
        <FL val="Carrier">
            <![CDATA[FedEX]]>
        </FL>
        <FL val="Excise Duty">
            <![CDATA[0]]>
        </FL>
        <FL val="Sales Commission">
            <![CDATA[0]]>
        </FL>
        <FL val="Status">
            <![CDATA[Created]]>
        </FL>
        <FL val="ACCOUNTID">639175000000054021</FL>
        <FL val="Account Name">
            <![CDATA[test account]]>
        </FL>
        <FL val="SMOWNERID">639175000000053003</FL>
        <FL val="Sales Order Owner">
            <![CDATA[Adam Wardle]]>
        </FL>
        <FL val="SMCREATORID">639175000000053003</FL>
        <FL val="Created By">
            <![CDATA[Adam Wardle]]>
        </FL>
        <FL val="MODIFIEDBY">639175000000053003</FL>
        <FL val="Modified By">
            <![CDATA[Adam Wardle]]>
        </FL>
        <FL val="Created Time">
            <![CDATA[2012-07-23 13:33:34]]>
        </FL>
        <FL val="Modified Time">
            <![CDATA[2012-07-23 13:33:34]]>
        </FL>
        <FL val="Sub Total">
            <![CDATA[4.5]]>
        </FL>
        <FL val="Tax">
            <![CDATA[0]]>
        </FL>
        <FL val="Adjustment">
            <![CDATA[0]]>
        </FL>
        <FL val="Grand Total">
            <![CDATA[4.5]]>
        </FL>
        <FL val="Product Details">
            <product no="1">
                <FL val="Product Id">639175000000054019</FL>
                <FL val="Product Name">
                    <![CDATA[HB Pencil]]>
                </FL>
                <FL val="Unit Price">1.5</FL>
                <FL val="Quantity">3.0</FL>
                <FL val="Quantity in Stock">47.0</FL>
                <FL val="Total">4.5</FL>
                <FL val="Discount">0.0</FL>
                <FL val="Total After Discount">4.5</FL>
                <FL val="List Price">1.5</FL>
                <FL val="Net Total">4.5</FL>
                <FL val="Tax">0.0</FL>
                <FL val="Product Description">
                    <![CDATA[null]]>
                </FL>
            </product>
        </FL>
        <FL val="Discount">
            <![CDATA[0]]>
        </FL>
    </row>
</SalesOrders>
```