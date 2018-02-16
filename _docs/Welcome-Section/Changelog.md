---
slug: changelog
redirect_from: "/article/44-changelog"
title: Changelog
---

## Release 2.13
###  New
 * Magento v2 - Upload Credit Memos - Added new task for creating credit memos
 * Sage 50 Payroll - Added a new connector with tasks for Upserting Employee Payments, Employee Deductions and Employee Absences into Sage 50 Payroll (more information available http://workflow.zynk.com/sage-50-payroll)
 * ProSKU - Export Stock - Added a task to the ProSKU library to support exporting stock based on the criteria provided in the task settings.
 * Shopify - Import Order Fulfillment - Added a task to support creating and updating order fulfillments in the Shopify ecommerce platform.
 * WooCommerce v3.0+ - Added a new connector which uses the latest version of the WooCommerce API, available since WooCommerce v3.0
 * Sage 200 Online - New library available to connect to Sage 200 Standard Online and Extra Online editions

###  Updated
 * Designer - Automatically expand all task settings
 * Sage 50 - Import/Export Invoices - Added support for the 'Due On' field
 * Sage 50 - Match Accounts On - Now support matching customers on extra fields. Email 2, Email 3, Telephone 2, Trade Contact, Custom 1, Custom 2 and Custom 3 are now all supported.
 * Sage 200 - Import Sales Orders - Now supports updating existing Live Sales Orders in Sage that have no allocated or despatched quantities. Order will be updated to reflect provided XML.
 * Sage 200 - Import Transactions - Suppress the error when the account is on hold
 * Salesforce - Complex Object Upload - Now support looking up the value of fields other than Id
 * WooCommerce v2.2+ - Download Tasks - Now supports complex meta data types, including objects and arrays
 * Magento v2 - Upload Products - Added support for looking up any select/multiselect attribute types and optionally creating where a match isn't found
 * Magento v2 - Upload & Download Tasks - Added support for reading custom values/objects/arrays returned via the API
 * Zip Search - Re install zip search from the extensions manager to see new features like optionally excluding files from search results and setting date time ranges.
 * Sage 200 - Import Customers - Now support setting the contact roles.

###  Fixed
 * Amazon Marketplace - All Tasks - Correctly set the Channels setting when upgrading from an older version of Zynk that didn't have the setting
 * BigCommerce - Download Products - Fixed issue with the task never downloading any products
 * JSON To XML - Now support transforming JSON array to XML. The provided Root Element Name will be used for the XML Root and Elements.
 * Magento V1 - Download Tasks - Correctly build up filters based on multiple fields
 * Magento V2 - Upload Products - Fixed issue setting the extension_attributes fields
 * Sage 200 v5 - Export Customers - Fixed the "Invalid object name 'Salutation'" error
 * Xero - Upload Tasks - Fixed issue with warnings not being written to the success files
 * Zynk Tasks - Fixed issue with Use output from previous task logic, was resulting in file names not being passed through correctly.
 * Magento V2 - Uploads - Fixed an issue where related collections not provided in the data are blanked out on Magento. E.g. When uploading products, if product images weren't specified in the data then the product images on Magento would be removed.
 * Magento V2 - Uploads - Fixed an issue where errors regarding data from Magento V2 were not being correctly captured, meaning that the cause of issues with data aren't obvious.
 * Zynk - Default Editor - Fixed an issue where the default editor wouldn't launch as expected.

## Release 2.12
### New
 * Magento v1 - Download store information from Magento
 * Magento v2 - Added Upload Shipments task
 * Peoplevox - New connector to integrate customers, suppliers. sales orders and more with Peoplevox warehouse management system

### Updated
 * BXP - Upload Records - Added support for referencing the generated ID of a parent record within it's related records
 * HTTP Task - Added a setting to compress data before sending it via HTTP POST, PUT, PATCH or DELETE
 * Sage 50 - Allocate Payments - Changed the Date From and Date To settings to Zynk Objects, to allow them to be set dynamically
 * Sage 50 - Update Ledgers - Optionally use customer order number to match an invoice.
 * Sage 200 - Export Customers - Now exports OverrideTaxCode, DUNSNumber, LastCreditReview, NextCreditReview, ApplicationDate and DateReceived
 * Sage 200 - Export Tasks - Now support retriving custom fields from custom join tables

### Fixed
 * BXP - Download Records - Fixed issue with the modified date setting not updating
 * BXP - Upload Records - Fixed the 500 error when the value of a match field contains an apostrophe
 * Ebay - Connection - Web browser was constanly refreshing
 * Sage 50 - Allocate Payments - Fixed the syntax error caused by account references containing an apostrophe
 * Sage 200 - Export Customers - Fixed issue which could prevent modified delivery addresses being exported

## Release 2.11.2
### Updated
 * Sage 200 - Export Suppliers V2 - Now exports analysis codes.
 * Sage 200 - Customers/Suppliers - Now supports setting and retrieving the MonthsToKeepTransactionsFor field.
 * Sage 200 - Customers & Suppliers - Now supports setting and retrieving the trading tab country code independently of the Main Address country code.
 * Sage 200 - Suppliers - Now supports setting and retrieving AdditionalReference, NonUKSortCode, BankPaymentReference.
 * Sage 200 - Suppliers - Now supports setting and retrieving the Payment Terms In Days field.

### Fixed
 * Sage 200 - Import Purchase Orders - Allow auto creation of 0 priced products.
 * Sage 200 - Export Suppliers V2 - Now exports email addresses correctly, was previously retrieving phone numbers in some instances.

## Release 2.11.1
### Fixed
 * Sage 200 - Export Suppliers - Exporting the same Contact for every supplier.
 * Sage 200 - Export Customers - Delivery addresses not belonging to Customer being exported.

## Release 2.11
### New
 * BXP - Added new connector for BXP, with upload and download records tasks
 * Connectwise - Added Upload Companies and Opportunities tasks
 * Magento v2 - Download Customer Groups - A new task that allows you to download all customer groups from Magento v2
 * Magento v2 - Update Inventory - A new task that can update inventory in Magento v2

### Updated
 * ConnectWise - Download Opportunities - Allow for the download of additional product information relating to opportunity line items
 * Email - Send Email - Added support for email addresses including a display name
 * FTP - Connection - Now test the credentials against the FTP server
 * Magento - Upload Inventory - Add in support to set manage_stock and use_config_manage_stock on Inventory tab in Magento v1
 * Zynk - Extensions - Add a shortcut to the start menu for installed extensions
 * Zynk - History Tab - Now show the what triggered each run of the workflow, added a button to view the workflow's archived data
 * Zynk - History Tab - Now show the position of each task in the workflow
 * Zynk - Submit Support Ticket - Fixed issue sending the emails, simplified the options for including additional info about the problem
 * Zynk - Task Library - Templates now appear in the task library. Restructured the task folders. Ctrl+F now focuses the search box. New tasks added to the workflow are auto selected.

### Fixed
 * File - File Repeater - Only update the Modified Since setting if the task ran successfully
 * Magento v2 - Matching on id for uploads
 * Magento v2 - Upload Tier Prices - Catch exception when price less than 0 is provided for a tier price entry
 * Sage 50 - Import Sales Orders - Replace the 'index was out of range' error with something more helpful when auto transfer BOM stock fails
 * Sage 50 - Import Sales Orders/Invoices - Net down the NetValueDiscount value when importing a VAT inclusive order
 * Xero - Upload Tasks - If an ExternalId is specified in the XML, it will no longer override the Id
 * XML - XML Merge - Make sure attributes are merged in subsequent file
 * Zynk - Clone Workflow - Copy the workflow's working directory instead of moving it

## Release 2.10
### New
 * Magento - New task to download all customer groups from Magento.
 * Sage 200 - Added Export Report task for Sage 200 v9 (2013) onwards
 * Sage 50 - Added new versions of the Update Sales Orders/Invoices tasks which accept Zynk XML input files
 * Zynk - In an open workflow, you can now see the number of tasks in use.

### Updated
 * Email - Send Integration Report - Added support for more data types
 * Sage 50 - Export Report - Support setting multiple values for a criteria, by setting the data type to a list
 * Sage 50 - Import Customers/Suppliers - Now read the default currency from Customer/Supplier Defaults when not specified in the XML
 * Sage 50 - Import Customers/Suppliers - Now validate provided currency code exists in the Sage 50 company
 * Sage 50 - Import Customers/Suppliers - Now validate provided tax code is valid
 * Sage 50 - Import Invoices/Purchase Orders - Now support the VatInclusive flag
 * Sage 50 - Import Transactions - Allow the Posted Date to be provided, will default to today's date if not specified in the XML
 * Sage 50 - Import Transactions - Default TransactionDate to today's date if not specified in the XML
 * Sage 50 - Import Transactions - Pick up the default nominal code from the customer/supplier when importing SI/SC/PI/PC transactions
 * Sage 50 - Import Customers/Suppliers - CompanyName is only required on new records.
 * Sage 200 - Import Customers/Suppliers - CompanyName is only required on new records.
 * Sage 200 - Import Goods Despatched Notes - Added 'Auto Acknowledge Order', 'Auto Print Order Invoice' and 'Auto Post Invoice' settings
 * WooCommerce - Upload Tasks - Improved handling of parse errors on the responses from the API, will now log a warning with details of the field that couldn't be parsed
 * Shopify - Download Orders - Add Download From date to task. Prevent orders from being missed in downloaded data.

### Fixed
 * Container/Repeater Tasks - Setting the 'Can Resume From Failure' setting to false now prevents its child tasks from resuming if they fail
 * Sage 50 - Connection - When editing an existing connection, the data path will no longer change if there is more than one company with the same name
 * Sage 50 - Import Sales Orders/Invoices/Purchase Orders - Only read the carriage tax code from VAT Settings on the task if enabled, otherwise use the default from the customer/supplier account
 * Sage 50 2017 - Import Transactions - When importing into a company where GBP is not the base, results in (Failed to import transaction : The Foreign Currency on the account does not match the Foreign Currency on the transaction.)
 * Sage 200 - Export Query - Now return the Fail result code instead of Success if the task can't connect to Sage
 * Zoho CRM - Download Records - Fixed issue where the task would always download all records when a filter was specified
 * Zynk - Always store the zynk.sdf and log.sdf files in C:\ProgramData\Zynk Software\Zynk\2.0\Data even if the working directory has been changed, to avoid issues accessing the files from a network location
 * Zynk - Resolved issues with the extension manager hanging after installs.
 * Zynk - Fixed instability issues with the History tab
 * Zynk - Fixed the 'max workflows reached' error after an exisiting license key is re-activated
 * Sage 50 - Export Transactions - Sage 50 (All / Modified) not exporting any transactions
 * Sage 200 - Import Sales Orders - Attempting to import an order with an inactive item results in the import failing
 * Sage 50 - Import Transactions - Application crash when trying to import certain transaction types (e.g. SalesPayment)

## Release 2.9
### New
 * Xero - Added download purchase orders and upload purchase orders tasks
 * Zynk - Statistics Start Page - View statistical data retrieved from the Zynk database and send to yourself via email in CSV or HTML format.

### Updated
 * Magento - Upload Shipments - Now supports receiving multiple item lines of the same sku code
 * Magento - Upload Shipments - Now supports specifying the item_id or sku
 * Magento V2 - Upload Products - Added support for automatically assigning and optionally creating product categories on Magento
 * Sage 50 - Import Customers/Suppliers - Now support importing/exporting the Email 2 and Email 3 fields
 * Sage 50 - Import Transactions - Now automatically set the TaxCode, TaxRate and TaxAmount for sales and purchase transactions if not provided
 * WooCommerce - Upload Products - Now support matching to multiple products with the same SKU. The task will update each matching product it finds
 * WooCommerce - Connection - Added option to ignore certificate errors
 * Xero - All Tasks - Added support for storing an ExternalId in the truth table, and using this to match existing records in Xero
 * Zynk Options - Added an option for setting the encoding used throughout the application
 * Zoho CRM - Download Records - Added a 'Download From' setting, which is now used instead of the Last Ran date when downloading modified records
 * Zoho CRM - Download Records - Add support for downloading single related records based on the foreign ID provided in the data

### Fixed
 * Brightpearl - Upload Orders - Fixed decimal precision error when automatically calculating tax amounts
 * Brightpearl - Upload Tasks - Fixed incorrect 'more than one match' errors when looking up matching records
 * EKM Powershop - Download Orders - Store the last download date in a Download From property as relying on Last Ran at task level causes some record changes to be missed
 * Magento - Upload Shipments - Invoice creation and capture creates an invoice for the entire order, rather than for the item quantities that have been shipped.
 * Magento - Upload Products - Removed field validation on fields which can be marked as 'not required' on
 * Magento V2 - Download/Upload Products - Fixed a 'Failed to parse the response from Magento.' message when working with Magento Products.
 * Sage 200 (V9, V10 onwards) - Import Customers/Sales Orders - Account Matching - Updated the account mapping to use the Sage 200 SDK to perform the lookup. (Stops database access errors occurring).
 * Sage 200 - Export Purchase Orders - PurcahseOrderDeliveryAddress now shows the correct telephone and fax numbers
 * Sage 50 - Import Purchase Orders - Automatically placing items on order resulted in the error "The product {0} either does not appear on purchase order {1}, or the quantity specified exceeds the amount to be delivered" when trying to import goods received notes
 * Salesforce - Complex Object Upload - Objects are now written to the success file even if a related object failed to upload. Still attempt to upload other related objects if one fails.
 * Zynk - Auto Mapper - Zynk XML Product to Magento V2 Product - not mapping price from Sage product
 * Zynk - Email Address Validation - Not allowing any email addresses with a TLD longer than 4 characters. Now supports up to 63
 * Zynk - Mappings Form - Updated the clipboard functionality to support pasting from spreadsheets (Google Sheets, Excel etc.)
 * Zynk - CSV Tasks - Now escapes field delimiters correctly (i.e. any instances of two field delimiters together will be escaped).

## Release 2.8
### New
 * Shopify - Added Upload Inventory task
 * Brightpearl - Added new connector for the Brightpearl online accounts system

### Updated
 * Sage 200 - v2 Export Tasks - Added basic support for getting custom field values from joined tables, only works where a single join is involved
 * Sage 200 - v2 Export Tasks - Now log custom fields and joins when debug logging is enabled
 * Sage 50 - Import Sales Orders - Optionally automatically create transfers for BOM products if there is not enough quantity available
 * Sage 50 - Import Transactions - No longer support sales discount transactions as its not valid to create these directly

### Fixed
 * Sage 200 - v2 Export Tasks - Fixed issues when using an alias for a custom field
 * Sage 50 - Import Purchase Orders - Now correctly calculate the tax amount for carriage
 * Sage 200 - Export Customers V2 - City, County and Country not reflecting the segmented address settings in Sage
 * Sage 200 - Import Transactions - Fixed issue with penny difference rounding issues, sometimes causing tax analysis does not match tax values errors

## Release 2.7.1
### New
 * ProSKu - New connector available for the warehouse management system, ProSku.
 * Sage 50 - Update Sales Orders - Update a single field on a Sales Order.

### Updated
 * Workflow Reports - Now show which tasks ran, including their status and in/out/error counts
 * Sage 50 - Import Stock Transactions - Now set Reference, Details etc. from XML input.
 * Sage 50 - Export Transactions - Now export the project reference and cost code
 * Sage 50 - Import Transactions - Now support setting the cost code field on purchase invoices/credits

### Fixed
 * Sage 200 - Export Query - Fixed the 'There is already an open DataReader associated with this command' error when using more than one export query task in a workflow
 * Sage 50 - Import Goods Received Notes - Now write any errors to the log and fail file
 * Sage 50 - Export Price Lists - Fixed the 'No connection' errors when running the task
 * Magento - Download Tasks - Fixed issue where filters checking for null values would not return any results

## Release 2.7
### New
 * Zynk - Auto Mappers - We now provide auto mappers for Kashflow and Sage One integrations.

### Updated
 * Sage 50 - Import Goods Received Notes - No longer required to provide AccountReference in object.
 * Sage 50 - Import Sales Orders, Purchase Orders and Invoices - Always round payment amount to 2 decimal places to replicate Sage 50's own functionality.
 * Zynk - Auto Mappers - Now able to add auto mappers between two external systems, e.g Kashflow to Magento, Magento to Sage One etc.
 * Sage 200 - Import Stock Records - Fail any products with an invalid supplier account reference, previously logged an error and still imported the product.
 * Sage 50 - Import Sales Orders, Invoices and Purchase Orders - Added validation for the tax code, nominal code and department.
 * Sage 200 - Import Stock Records - Automatically enable search category values on the product group, if not already enabled

### Fixed
 * Sage 50 - Import Stock Records - Only set ItemType when provided or creating a new product.
 * Sage 200 - Import Sales Orders - Fixed NullReferenceException in Sage v9 and above when the project code doesn't exist
 * WooCommerce - Download Orders - Meta data is now written to the output file when the setting is enabled
 * Magento - Upload Products - Fixed error when specifying a decimal qty
 * Sage 50 - Import Transactions - Only check for duplicates if an Id is provided in the XML
 * Zynk Upgrader - Now copy auto mapper files and fixed permissions issues with the copied files
 * Sage 200 - Export Stock Records - Now write search categories to the SearchCategories collection instead of Attributes
 * Task Scheduler - Fixed issue where schedules don't trigger on Windows 10
 * Sugar CRM - Connection - Fixed issue connecting to Sugar version 7.7.x.x
 * Amazon Marketplace - Upload Feeds - Fixed the 'Missing required parameter SellerId' error
 * Sage 50 - Import Sales Orders, Purchase Orders and Invoices - Added validation for the default product code setting

## Release 2.6
### New
 * WooCommerce - Added auto mappers for orders, customers and products
 * Sage 200 - Import Price Bands - Create and update price bands and selling prices
 * Kashflow - New connector that integrates with accounting web system Kashflow.
 * Options - Optionally select your own SMTP credentials to send workflow notification emails.
 * Sage 50 - Export Departments - A task to export departments from Sage 50.
 * Designer - Task Settings - Added drop down which allows values to be selected from the source data

### Updated
 * Magento - Upload Products - Added validation of required fields
 * Sage 200 - Import Purchase Orders - Now support setting analysis codes on item lines
 * Sage 200 - Import Transactions - Renamed existing Prevent Duplicates setting to 'Check References', added new Prevent Duplicates setting which checks the truth table
 * Sage 200 - Import Sales Orders - Now support setting the 'Show on customer documents' and 'Show on picking list' fields
 * Sage 200 - Export Stock Records - Added option to export product suppliers
 * Amazon - Download Orders - Optionally download a specific order by using the Order Id setting.
 * Amazon - Download Commissions/Orders/Refunds - Optionally specify a 'Download To' date to download orders between a specific time frame.
 * Amazon - All Tasks - Now configure which channels you wish to integrate at task level, also one connection supports all channels.
 * Sage 50 - Departments - Set department by name now on various import tasks using new department objects.
 * Sage 200 - Import Sales Orders - Now support setting the project analysis fields on item lines

### Fixed
 * Sage 50 - Email Invoices - Fixed issue setting the printed/emailed flags in Sage
 * Salesforce - Complex Object Upload - No longer check required fields are provided when updating an existing record
 * WooCommerce - Upload Customers - Fixed invalid email error when trying to create a new customer in WooCommerce

## Release 2.5.1
### Updated
 * Magento - Upload Products - Can now set the is_in_stock field manually via the XML

### Fixed
 * Sage 50 - Import Invoices - Fixed issue with the Default Account Reference setting not working
 * Quickbooks - Added missing dependency which prevented the connector from loading

## Release 2.5
### New
 * Amazon - Download Commissions - Retrieve the commission value of an order based on date
 * Amazon - Download Refunds - Retrieve refund value of an order based on date
 * Connection Failure Notifications - Can now get an email if Zynk can't connect to an external system. Currently only supported for Sage 50 UK, Sage 50 US, Sage 200, ACT, Magento V1 & V2, Salesforce, SugarCRM, Zoho CRM, Xero, WooCommerce, FTP, MS SQL, ODBC, OLEBD and SQLite
 * Extensions - Now install extra connectors from the extensions form.
 * Salesforce - Added Complex Object Upload task
 * My Mobile Workers - New connector for integrating Jobs, Items and Customers.
 * Quickbooks - Added new connector for Quickbooks

### Updated
 * Sage 50 - Export Price Lists - Add list of account references assigned to the price list.
 * Sage 200 - Export Sales Orders - Now export the delivery phone and fax numbers
 * Sage 200 - Import Transactions - Now support setting second reference on BankReceipt and BankPayment transactions
 * Sage 200 - Import Transactions - Now support importing non-taxable receipts and non-taxable payments against bank accounts
 * Amazon Marketplace - Connection - Added support for Canadian accounts
 * Amazon Marketplace - Download Orders - Added fulfillment channel option to specify whether to download FBA, non-FBA or all orders
 * Connection Wizard - Help button now takes you to the specific article for the type of connection you are editing
 * Designer - Now expand container tasks after moving an existing task into them
 * Database Connectors - Connections are now kept open and re-used between tasks
 * Report Emails - Improved the style of the reports, and updated all reports to use the same style
 * Sage 200 - Export Sales Orders/Purchase Orders - Now output both the Description and Text elements for free text lines, mimicking the fact that these are interchangeable in the import tasks
 * WooCommerce - Added support for the WC API Custom Meta plugin

### Fixed
 * Xero - Download Tasks - Filter setting is now applied to every page of records downloaded
 * File - If File Exists - Will no longer automatically create the file if it doesn't exist, causing the task to always return true
 * Sugar CRM - Connection - Will now automatically re-connect if the session ID becomes invalid
 * Log Database - Fixed issue with upgrade routine that prevented Zynk creating entries in the workflow history
 * CSV - CSV to XML & CSV Repeater - Now correctly handle delimited fields containing a line break
 * Sage 50 - Export Purchase Orders - When "Use Base Currency" is false, all values (net, tax and totals) were exported as 0
 * Sage 50 - Import Stock Transactions - Now reads out the generated StockTransactionNumber
 * WooCommerce - Download Tasks - Fixed issue which could cause some records not to be returned when downloading new or modified records
 * Designer - Fixed object reference error when clicking Run Workflow when there's no workflow open
 * Designer - Import Workflow - Fixed issue which caused auto mapper files to not be imported
 * Sage 50 - Export Tasks - 'NOT LIKE' operator now functions as expected.
 * Sage 200 - Traceable errors when trying to receive stock for traceable item on Sales return

## Release 2.4
### New
 * Sage One - Added new connector for Sage One

### Updated
 * Zoho CRM - Connection - Now support generating an auth token using an application specific password, and allow auth tokens to be entered manually where two factor auth is enabled
 * Zoho CRM - Download Records - Now support filtering records
 * Sage 200 - Export Sales Orders - Now export the project analysis fields on item lines
 * Sage 200 - Export Transactions - Now Export the project analysis fields
 * Sage 200 - Import Sales Orders - Now support creating quotes and pro formas
 * Sage 200 - Analysis Codes - updated the set analysis code value logic to add new values where they don't exist and the setting in sage permits (Add New On Entry is enabled)
 * Designer - Can now rename workflows by pressing F2
 * Sage 50 US - Now support Sage 50 US 2017
 * Sage 50 - Export Query - Added 'Export As Elements' option

### Fixed
 * Sage 50 - Email Invoices/Statements - Fixed object reference not set error when a CC and BCC address are not specified
 * Sage 50 - Dashboards - Sales Order and Invoice totals now take credits into account
 * Sage 200 - Import Sales Orders - Fixed issue where stock would only be partially allocated if negative stock levels are allowed and some (but not enough) free stock is available
 * Designer - Fixed error when trying to delete a template that has been added to the workflow
 * Sage 200 - Import Transactions - Always use exempt tax code for SR, SP, PR and PP transactions (any other tax code is not valid)
 * Sage 200 - Import Transactions - Always set a posted date on the transactions, prevents them appearing as deferred
 * Sage 200 - Import Sales Orders - Fixed object reference not set error when allocating an order that doesn't contain any lines that require allocation
 * Sage 200 - Import Sales Orders - Fixed error when trying to set a discount on a free text item
 * Sage 200 - Import Customers - Now match existing contacts correctly when only some of the name fields (Forename, Middlename and Surname) are provided
 * Sage 200 v9, v10, v11 - Export Tasks - Fixed error when exporting custom fields
 * Designer - Fixed unhandled exception when trying to delete a template that has been added to a workflow
 * Sage 50 - Import Customers - Fixed detached field error when creating a new delivery address
 * MS SQL, ODBC, OLEDB - All Tasks - Now log a more meaningful error message if no connection is selected in the task settings

## Release 2.3
### New
 * Sage 50 - Added Export Couriers task
 * Sage 50 - Added Export SDO Query task
 * Sage 200 - Added connector for Sage 200 2016 (v11)

### Updated
 * SMTP Connection - Now validate the server and port settings
 * Sage 200 - Update Sales Orders - Now support updating the priority field
 * Sage 50 - Import Sales Orders - Now set the global department to the customer's department if not specified in the XML
 * Sage 50 - Import Invoices - Now set the global department to the customer's department if not specified in the XML
 * Sage 200 - Import Transactions - Now support importing JD and JC transactions as part of a group with a SI, SC, PI or PC transaction
 * Sugar CRM - Upload Records - Added settings to choose whether to perform an insert, update or upsert operation against Sugar

### Fixed
 * FTP Rename - Fixed issue with some FTP servers when checking if the file exists
 * Sage 200 - Export Customers - Fixed issue where contacts would not export if there was only one associated with the account
 * Sage 200 - Export Tasks - Fixed issue where custom where clauses would have no effect when the task is set to export all records
 * Sage 200 - Import Sales Orders - Fixed object reference error when auto creating products and no default warehouse is provided, or the warehouse provided doesn't exist
 * Workflows - Now only resume a workflow if the 'Resume Workflow on Failure' setting is true
 * Sage 50 - Export Inventory - Exports to incorrect XML structure /Company/Inventory/Inventory
 * Sage 200 - Import Transactions - Fixed issue with the rounding of tax amounts
 * Sage 50 - Export Customers - Fixed issue where customers without a delivery address were not exported when the Export Delivery Addresses setting was enabled
 * Zoho CRM - Upload Records - Task will no longer fail if the input file contains records with an error collection
 * Zynk Objects - Razor - Fixed issue where Zynk could hang if the value returned by the script contained a @ symbol
 * Data Tab - Changes to the internal or external IDs are now saved
 * Magento - Download Tasks - Fixed error if filtering on the created_at or updated_at field

## Release 2.2
### New
 * Extensions - Extensions Manager now allows the download of useful tools such as Zip Search, ZLM and XSLT Builder.

### Updated
 * Sage 50 - Export Customers - Added option for exporting multiple delivery addresses
 * Sage 50 - Import/Export Sales Orders - Added support for the new custom fields in Sage 50 2016
 * Sage 50 - Import/Export Purchase Orders - Added support for the new custom fields in Sage 50 2016
 * Sage 50 - Import/Export Invoices - Added support for the new custom fields in Sage 50 2016
 * FTP - Rename - Now support overwriting existing files
 * Task Library - Tasks are now grouped by system type
 * Sage 200 - Export Suppliers - Now export bank infomation
 * Sage 50 - Import Purchase Orders - Added support for auto creating suppliers
 * Zynk Objects - Files can now be dragged and dropped onto the form, which automatically sets the value
 * Sage 200 - Import Stock Transactions - Added a prevent duplicates setting
 * Sage 50 - Email Invoices/Statements - Added CC and BCC settings
 * Sage 200 - Export Customers - Added contact roles to the contact export

### Fixed
 * On Failure Tasks - Fixed issue where tasks which use a connection would fail with an 'object reference not set to an instance of an object' error
 * Designer - Fixed application hanging when dragging a container/repeater task into one of it's own child container/repeater tasks

## Release 2.1.8
### New
 * Email - Send Integration Report - Added new task for generating and sending a report based on success/fail files
 * Designer - Workflows can now be ran without having to save them first
 * Workflows - Can now resume from where they last finished if an error occurred
 * Mappings - Can now define mappings between data from different systems (e.g. Magento shipping method > Sage additional charge), which can be used in XSLT via the MapTo and MapFrom functions
 * Twitter - A twitter connector that allows you to download followers, retweets, mentions etc. and upload tweets.
 * LinkedIn - A LinkedIn connector that allows you to download your profile information.
 * Ebay - Added Upload Inventory task
 * Magento V2 - Added new Magento V2 connector

### Updated
 * Sage 50 - All tasks - Connection is now kept open and re-used between tasks
 * Sage 200 - All tasks - Connection is now kept open and re-used between tasks
 * Magento - All tasks - Connection is now kept open and re-used between tasks
 * Salesforce - All tasks - Connection is now kept open and re-used between tasks
 * Sugar CRM - All tasks - Connection is now kept open and re-used between tasks
 * Sage 50 US - All tasks - Connection is now kept open and re-used between tasks
 * ACT - All tasks - Connection is now kept open and re-used between tasks
 * Sage 200 - Import Customers - Added support for setting the payment basis field
 * Campaign Monitor - Upload Subscribers - Added resubscribe setting
 * Installer - The installer is now signed and will show the publisher as 'Zynk Software'
 * Sugar CRM - Query - Now uses pagination to download the results in a series of batches
 * Sage 50 - Export Invoices - Now export the GlobalNominalCode, GlobalDetails, NetValueDiscountDescription, NetValueDiscountComment1 and NetValueDiscountComment2
 * eBay - Download Orders - Now expose a property 'Include Item Specifics', resulting in extended item information being downloaded (including MPN) with each order
 * eBay - Download Listings - Now expose a property 'Include Variations', resulting in extended variant (option) information being downloaded (including MPN) with each listing
 * Schedule - Default the 'Configure for' setting to highest version supported by the OS
 * Designer - Now show a status icon next to each task when running a workflow
 * Sugar CRM - Upsert Task - Support matching on multiple key fields
 * Sage 50 - Connection - Improved wording of the error messages

### Fixed
 * ACT! - Export Contacts - No contacts exported when exporting modified.
 * CSV to XML - Now handle invalid XML characters in the column names correctly
 * XML to CSV - Still output the header if the input file contains no data when using a custom mapping
 * Sugar CRM - Upsert - Fixed error when matching existing records if the key field's value contained an apostrophe
 * Sage 200 - Sales/Purchase Traceable adjustments - Stock items with non-standard casing (some lowercase and some uppercase characters) not identified
 * Sage 200 - Import Stock Transactions - Errors being thrown if the item being processed is not set up as a traceable item in Sage
 * Sage 200 - Export Goods Despatched Note - Orders with only non-traceable item's despatches are not correctly picked up when Export Traceable Items is set to True
 * Sage 200 - Export Goods Despatched Note - Multiple traceable despatches not picked up in export
 * Sage 200 - Export Purchase Orders - Header custom fields not being exported
 * Zynk Core - Razor Engine - @@ can now be used to escape the razor instruction (@)
 * Sage 200 - Sales/Purchase Traceable adjustments - Traceable batch attributes not found on import
 * Sage 50 - Import Sales Orders / Invoices - Convert To Account Currency setting now converts unit and net value discount amounts
 * Sugar CRM - Upsert Task - Fixed error when looking up existing records by a key field where the module name is different to the table name

## Release 2.1.7
### New
 * Sage 50 - Update Ledgers - Added task to post invoices to the ledger
 * ACT 2016 - Added new ACT 2016 connector

### Updated
 * Xero - Download Tasks - Added a separate setting for the download from date, no longer uses last ran
 * CSV Library - Added support for setting the encoding to be used when processing the Input CSV File
 * Sage 50 - Import Purchase Orders - Added support for automatically setting the stock as 'on order'
 * Sage 50 - Import Despatch Notes, Goods Received Notes and Stock Transactions - Added prevent duplicates setting
 * Sage 200 - Import Despatch Notes, Goods Received Notes and Stock Transactions - Added prevent duplicates setting
 * Salesforce - Create, Update and Upsert Tasks - Now log any error message returned by the API

### Fixed
 * Magento - Upload Group Prices - Fixed issue setting the standard price on products
 * Sugar CRM - Upsert - Fixed issue when looking up the record IDs to set in link fields
 * Sage 50 - Import Sales Orders - Fixed issue where company name on sales order is empty if Company on SalesOrderAddress in XML is empty, now uses the FullName (Title, Forename, Surname)
 * CSV Library - Normalised the terminology used in the tasks.
 * XML Select - Fixed object reference exception when the XPath query does not return a result

## Release 2.1.6
### New
 * Sage 200 - Update Purchase Orders - Allows for purchase orders/returns to be adjusted (received/returned).
 * Linked In - New Linked In connector to be used for downloading your profile.
 * Campaign Monitor - Download Lists

### Updated
 * Sage 200 - Import Goods Received Notes - AccountReference is no longer mandatory, it will be looked up based on the OrderNumber if not provided.
 * Sage 200 - Import Goods Received Notes - Now support setting the warehouse and bin.
 * Sage 200 - Update Sales Orders - Now support sales order/return adjustments
 * Sage 200 - Export Goods Despatched Notes - Added support for exporting traceable item details
 * Sage 200 - Export Stock Records - Fixed issue where incorrect stock nominal code was exported
 * Sage 200 - Export Stock Records - Now export the revenue, accrued receipts and issues nominals
 * Web Automation - Now implemented using Selenium + PhantomJS, enabling support for javascript

### Fixed
 * Sage 200 v9/10 - Export Stock Records - Fixed the ""StockItemPrice" and "StockItemPrice" in the FROM clause have the same exposed names" error.
 * Sage 200 v9/10 - Export Stock Records - Fixed issue with filtering on new records
 * Sage 200 - Export Sales Orders - Fixed issue where multiple despatches would cause item lines to be duplicated in the XML
 * XML Dashboards - Fixed issue reading the value returned by the XPath query
 * Sage 50 - Import Sales Orders - Fixed issue with looking up the unit price of item lines in Sage when not provided in the XML
 * FTP Repeater - Fixed issue with context variables being incorrectly calculated, causing unexpected errors.

## Release 2.1.5
### Fixed
 * FTP - Upload - Fixed temporary upload settings issue.
 * Zynk - Core - Fixed issue with errors on sql ce internal log database.

## Release 2.1.4
### New
 * Magento - Added Upload Product Images task
 * Designer - Added a notifications section, summarising recent workflow runs and failures

### Updated
 * HTTP Task - Added additional debug logging.
 * Sage 50 - Export Query - Can now specify a list of tables to check the modified date against.
 * XSLT Transform - Added support for xsl:message, messages can be logged as debug messages or to a file.
 * XSLT Transform - Added extension objects with common date, file and node functions.
 * Ebay - All Tasks - Now use the latest version of the API (947).
 * Designer - Updated the logo and branding.
 * Logs - All log data is now stored in a separate Log.sdf file.
 * Sage 200 - Export Sales Orders - Now export the ProjectRef and ProjectItem for item lines.
 * Sage 200 - Import Goods Received Notes - Now support setting the alternative ref field on traceable items.
 * Sage 50 - Email Statements - Now allow a custom date range to be specified for the transactions.

### Fixed
 * Designer - Fixed case sensitivity issue on the file extension when opening a workflow.
 * Sage 200 - Import Stock Records - Fixed error that would occur when trying to set the fulfilment method on a new product to FromSupplier.

## Release 2.1.3
### Fixed
 * XSLT Transform - Now calculate the parameter values before the output file is prepared for writing.
 * Sage 50 - Import Sales Receipt - Don't prevent tax amount from being set, VAT is valid on SR's if VAT cash accounting enabled.

## Release 2.1.2
### New
 * XSLT Builder - Added tool for writing and testing XSLT transforms.

### Updated
 * Sage 50 - Export Tasks - Updated the description on the export settings to reflect the current logic for determining new/modified records
 * Sage 50 - Export Tasks - Updated the Query Settings to support specifying how clauses will be built up (AND or OR)
 * Sage 50 - Export Reports - Readded support for XLS and XLSX file type.

### Fixed
 * Schedule - Fixed error when trying to change the location or group.
 * Sage 50 - Export Transactions - Fixed an issue with how the query was being built up.
 * Zynk - Set Variable Task - Variable values are now calculated when the task is ran, rather than each time the variable is accessed.
 * Razor Scripts - Now correctly calculate the value of Zynk Objects used in the script.
 * Zynk Objects - Read Contents of File option - Fixed the 'Cannot access the file because it is being used by another process' error when reading a file that is already open.
 * File - File Repeater - Fixed issue where some modified files could be skipped if there was another file modified more recently in the same folder.
 * Sage 50 - Import Sales Orders - Fixed issue where the item description would not default to that on the product record if the SKU contained leading/trailing whitespace.
 * Sage 200 - Export Customers - Fixed issue with the wrong values being exported to the website and mobile fields on contacts.

## Release 2.1.1
### New
 * Zynk - Stop Repeater - Added new task for breaking out of repeaters.
 * Dashboards for Sage 50 UK - Added support for quotes.
 * Dashboards for Sage 50 UK - Added support for transactions.
 * Dashboards for Sage 200 - Added support for transactions.
 * HTML - HTML to XML - Added new task for converting HTML to XML.
 * Sage 200 - Update Sales Orders - Added new task for updaing analysis codes on existing orders.

### Updated
 * Options - Added settings for changing the supported SSL/TLS versions.
 * HTTP Task - Addded option for setting the protocol version, defaults to 1.1.
 * Dashboards - Split the list of available values into two separate drop downs, for module and value.
 * WooCommerce - Upsert Products - Now match existing product variations based on SKU.
 * Shopify - Upsert Customers - Now match existing customers based on email address.
 * FTP - Added support for a new format of FTP server.
 * Zynk Data Upgrader - Added option to not run the upgrade.
 * Sage 200 - Import Customers - Now support setting the account status field.

### Fixed
 * Backups - Fixed the 'size was 0, but I expected XXXXX' error.
 * Licensing - Now correctly check the number of tasks in a workflow.
 * Dashboards for Sage 50 UK - Sales order values now exclude quotes and proformas.
 * Dashboards for Sage 200 - Sales order values now exclude returns.
 * Sage 50 - Import Transactions - Ignore the TaxAmount on sales receipt transactions, as its not valid to specify this value.
 * WooCommerce - Upsert Products - Fixed issue setting quantity in stock for product variations.
 * Sage 200 - Import Suppliers - Issue where payment group information was flattened on Sage 200 suppliers updated by Zynk, even when payment group not provided in XML.
 * Truth - Issue with retrieval of matching records where if no Id node provided in data (e.g. CustomerId, SupplierId), the first matching InternalId to that type is retrieved from the Truth.
 * Zoho - Upserting Records - Issue uploading data containing special characters (e.g. &).
 * Email Repeater - Fixed issue with the message body variable not being populated in certain conditions.
 * Sage 50 - Import Invoices - Price calculations now take the decimal precision setting in Sage into account.
 * Sage 50 - Import Sales Orders - Price calculations now take the decimal precision setting in Sage into account.
 * Sage 50 - Import Invoices - Now default the SKU code to S3 when importing service invoices.

## Release 2.1.0
### New
 * Dashboards for Sage 50 UK - New connector for building dashboards for Sage 50.
 * Dashboards for Sage 200 - New connector for building dashboards for Sage 200.
 * Dashboards for Salesforce - New connector for building dashboards for Salseforce.
 * Dashboards for SQL - New connector for building dashboards for SQL databases.
 * Dashboards for XML - New connector for building dashboards for XML data.
 * Magento - Upload Invoices - Added a new task for uploading invoices to Magento.
 * Magento - Upload Shipments - Added a new task for uploading shipments to Magento.
 * Salesforce - Upload Prices - Added task for updating pricebooks, supports multiple currencies.
 * Web Automation - New task for automating web processes.

### Updated
 * Designer - Logs - Logs are now displayed in a single list, with buttons to show/hide info, debug, warning and error messages.
 * Designer - Connections can now be removed from tasks.
 * All Tasks - Added an option to enable/disable debug logging, by default it is disabled
 * Sage 50 - Connection - No longer store the version number as part of the connection, will now connect to a new version of Sage automatically if the data path hasn't changed.
 * Sage 50 - Import Stock Records - Added pre-validation of the products.
 * Sage 200 - Import Customers - Added support for setting the credit reference field.
 * Sage 200 - Import Customers - Added support for setting the account on hold field.
 * Sage 200 - Export Customers - Now export the credit reference field.
 * Sage 200 - Import Stock Transactions - Added support for setting the debit/credit nominal analysis.
 * Sage 200 - Export Stock Transactions - Export the debit/credit nominal analysis lines if the nominal ledger was updated.
 * Sage 200 - Export Query - Now has a single Query setting which can be edited using the query designer, and support for updating the OpLock based on multiple tables
 * Sage 200 - Import Despatch Notes - Added support for matching to orders based on the customer order number.
 * Sage 200 - Import Stock Transactions - Now write the ID to the success file.
 * Shopify - All Tasks - Now connect to Shopify as a private app.
 * History Tab - Added refresh button.
 * WooCommerce - Upload Tasks - Added validation for required fields.

### Fixed
 * Designer - Improved error handling when loading/saving workflows.
 * Designer - Now displays correctly when using non-standard windows themes.
 * Designer - Now associate workflow package files (.wpk) with Zynk, allows import of workflows directly from the file system.

## Release 2.0.3
### Updated
 * Sage 200 - Import Goods Despatched Notes - Added option to auto allocate stock
 * Sage 200 - Import Stock Records - Added support for setting custom fields
 * Sage 200 - Import Stock Transactions - Added support for setting the cost price field
 * Schedules - Now set 'Run with Highest Privileges' to true and 'Do not store passwords' to false by default
 * Xero - Now connect using the private API
 * Zoho CRM - Added all standard modules to the list of record types
 * Zoho CRM - Added support for matching related records based on an external ID in the truth table

### Fixed
 * Sage 50 - Export Sales Orders/Invoices - Fixed issue where the quantity would export as 0 if it was not a whole number
 * Sage 50 - Import Invoices - PricesIncludeTax rounds correctly.
 * Sage 50 - Fixed issue detecting whether Sage is installed
 * Zynk - Set Variable - Fixed issue where razor scripts which raed the current value of the variable would cause Zynk to hang

## Release 2.0.2
### New
 * Zynk - Truth Tasks - Added a Insert into Truth task.
 * Zynk - Truth Tasks - Added a Update Truth task, allows for on custom criteria.
 * Zynk - Truth Tasks - Added a Delete from Truth task, allows for on custom criteria.
 * Zynk - Truth Tasks - Added a If Truth Contains task, allows for on custom criteria.
 * XML - Select XML Task - Added a Select XML task, allows for a value at a given XPath to be retrieved from XML (and optionally stored in a variable).

### Updated
 * Zynk Objects - Can now lookup a value from another task's settings
 * Sage 50 - Import Stock Records - Can now set the Inactive flag on products
 * Sage 50 - Export Stock Records - Now export the Inactive flag on products
 * Data Tab - Added search functionality
 * Sage 200 - Import Purchase Orders - Can now set the confirmation method on free text lines
 * Salesforce - Can now specify which API version to use

### Fixed
 * Sage 50 - Export Tasks - Fixed object reference not set to an instance of object error when running export task within a repeater.
 * Sage 50 - Export Invoices - Fixed negative values appearing on product credit invoices
 * Sage 50 - Import Sales Orders/Invoices - Default QtyOrdered on carriage to 1, preventing the price being calculated as 0 if a quantity is not specified
 * History Tab - Fixed the default ordering of the log entries
 * Zynk - Set Variable Task - Razor values are now calculated when the task is ran, rather than each time the variable is accessed

## Release 2.0.1
### Updated
 * Sage 200 - Import/Export Customers - Now support importing/exporting Credit Reference
 * Sage 200 - Import/Export Customers - Now support importing/exporting Trading Terms
 * Sage 200 - Import/Export Customers - Now support importing/exporting Sales Invoice Layout
 * Sage 200 - Import Stock Records - Now support assigning Warehouses to products on import (Warehouse must already exist)
 * Sage 200 - Import Stock Records - Now automatically assign search categories to the product group if it is not already assigned
 * Connections - Optional properties are now explicitly marked

### Fixed
 * Sage 200 - Export Goods Despatched Notes - Now export custom fields at both the despatch note and items level, UniqueId now contains the correct values
 * Sage 200 - Export Query - Fixed error caused by column names containing invalid characters for XML element/attribute names, invalid characters are now escaped

## Release 2.0
### New
 * Connection Manager - Connection details are no longer stored in workflow variables, and are now stored in the Connection Manager.
 * Facebook - Added Facebook connector, with tasks to get pages and post status updates.
 * Twitter - Added Twitter connector, with tasks to get favourites, followers, messages and timeline, and publish tweets.
 * Sage 50 US (BETA) - Added Sage 50 US connector, with tasks to import customers and sales orders, and export inventory.
 * WooCommerce - Added WooCommerce connector.
 * Task Library - The task library is now searchable.
 * My Workflows - Added functions to import/export workflows and their data.
 * SQL Select tasks - Added a graphical query builder.
 * Input/Output File Settings - Most tasks now have default input/output file names.
 * Data Upgrader - Upgrades all data for compatibility with Zynk v2.
 * Zynk CSV to Zynk XML - Transform .csv files directly into Zynk XML format.

### Updated
 * Zynk Designer - Changed the appearance of the designer. Added new icons and updated the menu and toolbar options.
 * Zynk Designer - Added a context menu to the task list.
 * Zynk Designer - Now cache the task library, significatly speeds up application load time.
 * Zynk Designer - Removed debugging options.
 * Zynk Designer - Removed the welcome screen.
 * Zynk Options - Optionally use your default text editor instead of the Zynk editor.
 * Zynk Object Editor - Redesigned the Zynk object editor, type is now selected using a drop down.
 * Zynk Object Editor - Will now open large files in an external application.
 * Workflow Schedules - Redesigned the schedule form, gives much greater control over the schedule.
 * Workflow Templates - Templates are now added to the currently open workflow.
 * Workflow Templates - Workflows can now be saved as a template.
 * JSON - JSON to XML - Now supports reading static text as the input.
 * Magento - Update Orders - Can now specify the comment in the input XML file.
 * Magento - Update Orders - Added 'Prevent Reprocessing' option.
 * Magento - Upload Inventory - Added success/fail files.
 * Magento - Upload Prices - Added success/fail files.
 * Sage 50 - Import Sales Orders - Now only support payments with order of type 'Payment already received'. Will automatically create an SA transaction for the payment amount.
 * Sage 50 - Export Report - Removed the unsupported export types.
 * Sage 200 - Export Tasks - Corrected the In/Out/Error counts shown on the history tab.
 * Sage 200 - Export Inventory - Added setting to enable/diable the export of traceable item details.

### Fixed
 * File Repeater - Processing modified files only - File changes made around the time of Workflow running were sometimes missed.
 * Truth Table - Fixed issues with sorting.
 * Zynk Designer - Imporoved error handling when opening workflow files.
 * ACT - All Tasks - Fixed error when a standard field has been deleted.
 * Amazon S3 - Updated to the latest SDK version, fixes issues with tasks not working.
 * Sage 50 - Login - Fixed missleading error when an invalid manual data path is provided.
 * Sage 200 - All Tasks - Fixed object reference error when their is an error in the input XML.

## Release 1.6.27
### New
 * Tesco - Added Tesco Marketplace Module, tasks to download orders, update orders (acknowledge/cancel), update inventory, upload product listings, upload product images an upload shipments
 * NetDespatch - Added NetDespatch Module, tasks to create new jobs or update jobs (cancel)

### Updated
 * CoreCommerce - Download Products - Added options to exclude product image information
 * Magento - Upload Products - Added should_create and should_update flags in the XML, to control whether to create or update the product in Magento
 * Auto Mapper - Magento Orders to Zynk Sales Orders/Invoices - Correctly map configurable products to a single item line
 * Sage 200 - Import Stock Records - set the Allow sales orders (AllowSalesOrder in XML) field
 * Sage 200 - Import Stock Transactions - Supports replication of a transfer in Sage, using StockTransactionType of Transfer.
 * Truth Records - Updated to allow for external id's up to 4000 characters (prevent truncation errors on Import into Sage)

### Fixed
 * CoreCommerce - Upload Products - Resolved timeout issues related to product get requests (previously returning base64 image information as well, increasing the request size)
 * JSON - JSON to XML - Validate XML output before writing to Output File.
 * Sage 50 - Export Inventory - Previously export as Company/Inventory/Inventory instead of the correct Company/Inventories/Inventory which is used in the connect object model
 * Sage 200 v8 (2011) - Import Purchase Orders - Fixed issue setting the Project Code and Project Item fields on free text items
 * Sage 200 - Import Stock Records - Don't require the product name to be provided if the stock record already exists in Sage 200
 * Channel Advisor - Download Orders - Update the Date From date based on the highest modify date in the data rather than the time that the task last finished running

## Release 1.6.26
### Updated
 * Sage 200 - Import Sales Orders - Added options to auto allocate stock always, as Sage or never
 * Sage 200 - Import Sales Orders - Made the validation of delivery dates optional
 * Sage 200 - Import Stock Records - Added support for importing NonStock and Miscellaneous products
 * Sage 200 - Import Stock Records - Now supports setting the default nominal specification for the Stock, Revenue, AccruedReceipts and Issues (StockNominal, RevenueNominal, AccruedReceiptsNominal and IssuesNominal on Product). See Analysis section of http://zynk.apidoc.io/zynk-xml-for-sage-200/import-stock-records for more details.
 * Salesforce - Bulk API Tasks - Added support for connecting to a sandbox

### Fixed
 * Upsert Truth - Correctly set the type when creating new records
 * Sage 200 - Import Purchase Orders - Purchase Orders can now be imported against supplier accounts where the balance exceeds the credit limit.
 * Salesforce - Upload Products - Fixed issue with prices when multi-currency is enabled in Salesforce
 * Salesforce - Upload Products - Prices will no longer be set to 0 if not provided in the input file
 * Salesforce - Upload Products / Upload Records / Bulk Salesforce - Now correctly derive the salesforce instance name if made up of multiple parts e.g. https://my.domain.salesforce.com
 * Sage 200 - Import Purchase Orders - Auto Create Products now sets the created stock item's Default Stock Nominal Analysis information based on the NominalCode, CostCentre and Department on the item line.
 * Sage 200 - Import Sales Orders - Auto Create Products now sets the created stock item's Default Revenue Nominal Analysis information based on the NominalCode, CostCentre and Department on the item line.
 * Sage 50 - Export Sales Orders / Export Purchase Orders / Export Invoices - Now exports records following update of the item line information - e.g. update of allocated/received amounts.
 * Sage 50 - All Exports - Now correctly set the hash (used for tracking changes to objects) based on the item line changes as well.
 * Sage 50 - Export Pricelists - If Recalculate Prices setting is enabled on task and the price in Sage uses the 'plus adjustment' value now derives the correct price, previously coming up with incorrect values.

## Release 1.6.25
### Updated
 * Sage 50 - Email Invoices - No longer delete the invoice query result when running in test mode
 * Sage 50 - Email Statements - Added option to include all tranasactions on the statements
 * Sage 50 - Email Statements - No longer delete the statement query result when running in test mode
 * Sage 200 - Import Purchase Orders - Added auto create products option

### Fixed
 * Sage 50 - Import Tasks - Now validate the success/fail file setting before running the import
 * Sage 200 - Import Tasks - Now validate the success/fail file setting before running the import
 * Sage 200 - Export Query - Fixed index error when Export All is set to false

## Release 1.6.24
### New
 * Added Sage 200 v10 (2015) connector

### Updated
 * Automapper - eBay - Supports variation listings
 * Sage 50 - Email Statements/Email Invoices - Added a 'Retain Generated Reports' option to the task. Set to true if you would like the generated reports to remain in the Zynk working Workflow directory (i.e. for archiving) or set to false if you would like the generated reports to be deleted by Zynk once they have been emailed.

### Fixed
 * Sage 50 - Import Transactions - Journal imports could allow for mismatching values where a debit/credit failed to import due to invalid nominal
 * Sage 200 - Export Stock Records - Fixed issue with the query
 * Sage 200 - Export Query - Fixed issue when exporting records with large OpLock values

## Release 1.6.23
### Updated
 * Sage 200 - Export Query - Now supports the query timeout setting to resolve issues with exporting large data sets

### Fixed
 * Sage 200 - Export Stock Records - Convert all OpLock values to big int to prevent issues with large OpLock values
 * Sage 200 v9 and v10 - Login Form - Fixed issue where the login form would display each time the workflow runs

## Release 1.6.22
### Fixed
 * Sage 50 - Import Invoices - Fixed issues with the Sku validation when importing service invoices

## Release 1.6.21
### Fixed
 * Web - HTTP Task - Correctly set timeout, previously wasn't setting all timeouts meaning that the task could sometimes take the default 5 mins before actually timing out
 * Amazon - Amazon Marketplace - Fixed issue with upload feeds not working, would complain about missing file 'MarketplaceWebService.dll' when running any of the upload feed tasks

## Release 1.6.20
### Fixed
 * Workflow Data Tab - fixed issue where multiple records incorrectly updated when editing truth records
 * Amazon Module - Fixed issue with Zynk installer

## Release 1.6.19
### New
 * ACT! 2015 - Added ACT! tasks (Import/Export Companies/Contacts/Opportunities/Products)
 * Amazon Vendor Central - Download Purchase Orders, Upload Purchase Order Responses/Despatch Advice/Invoices

### Updated
 * Amazon - All Tasks - Now support the MWSAuthToken parameter
 * Sage 50 - Export Tasks - Store a hash for each record to prevent the tasks exporting all records when the Sage recovery tools are used
 * SFTP - Upload - Now support providing the file content as static text
 * Sage 200 - Export Tasks - Added support for 'Characters To Cleanse', if receiving errors on export to do with invalid characters, these can now be stripped out during the import.

### Fixed
 * Sage 200 - Export Tasks - Query Timeout setting now works correctly
 * Sage 200 - Import Sales Orders - Added prevalidation of the delivery dates to prevent the task failing if the date is in the past
 * Sage 50 Import Sales Orders/Invoices - Fixed issue where orders/invoicescould be imported without an account reference when auto create accounts was enabled but the account reference generation was disabled

## Release 1.6.18
### Updated
 * Magento - Update Orders - Added Prevent Reprocessing option
 * ConnectWise - Download GL Batch - Thru Date property now supports Zynk Objects (meaning caluclated/rolling dates can be used)

## Release 1.6.17
### Updated
 * Sugar CRM - Upsert - Now support matching with existing records based on the value of a given field
 * Sage 200 - Import Goods Despatched Notes - Added support for custom fields on despatch note and despatch lines

### Fixed
 * Sage 200 - Export Sales Orders - Certain fields where missing from the output file when exporting from Sage 200 v9 (2013)

## Release 1.6.16
### Updated
 * Sage 50 - Import Customers - Added support for specifying custom regular expression for stripping out unwanted characters in any generated account references (only applies when using Account Generation Settings).
 * Sage 50 - Import Sales Orders - Added support for specifying custom regular expression for stripping out unwanted characters in any generated account references (only applies when using Account Generation Settings).
 * Sage 50 - Import Invoices - Added support for specifying custom regular expression for stripping out unwanted characters in any generated account references (only applies when using Account Generation Settings).

### Fixed
 * Magento - Upload Categories - parent id and name incorrect in success file for newly created categories
 * Sage 50 - Export Customers - Fixed issue with IsActive flag logic
 * ConnectWise - Update Invoice Payments - Would never log if an update call failed

## Release 1.6.15
### New
 * Sage 200 - Import Goods Despatched Notes - Now write out the Despatch Note DocumentNo in the success file
 * Sage 200 - Import Goods Despatched Notes - Now support the setting of custom fields on the import

### Fixed
 * Sage 200 - Import Goods Despatched Notes - Sage internal reference of goods despatch note wasn't always correct

## Release 1.6.14
### New
 * ConnectWise - Added Support for downloading detailed invoice information

### Fixed
 * Sage 50 - Import Customers - Fixed issue with logic surrounding the Inactive flag in Sage (based on the IsActive flag in the XML)

## Release 1.6.13
### Updated
 * FTP - FTP Repeater - Added a search pattern setting, which allows the results to be filtered
 * FTP - List Files - Added a search pattern setting, which allows the results to be filtered
 * Magento - Download Tasks - Now write the local date/time to the log when downloading modified records instead of the UTC date/time
 * Sage 200 - Import Customers - Added account reference convention setting
 * Sage 200 - Import Stock Transactions - Now allows stock transactions to take the stock level below the minimum quantity / above the maximum
 * SFTP - All Tasks - Added support for public key authentication

### Fixed
 * All Conditional Tasks - Now break on failure if a sub-task fails
 * Dropbox - Fixed issue with a 404 error when authorising Zynk to access Dropbox
 * Sage 50 - Import Invoices - Duplicate error message is now included in the fail file
 * Sage 50 - Import Purchase Orders - Now logs the error message if a nominal code is not valid, previously the order would fail to import without any reason
 * Sage 200 - Import Sales Orders - If the payment method specified in the input file does not exist in Sage the order now fails to import
 * XML - XML Merge - Now log a warning if the input file list contains the output file, previously caused a 'Process cannot access file' error
 * Sage 50 - Exports - fixed an issue where custom fields on nested objects (e.g. Sales Order Items) come through as a custom field on the parent object (e.g. Sales Order)

## Release 1.6.12
### Updated
 * Sage 200 - Import Goods Despatched Notes - Success file now contains the Sage internal reference

## Release 1.6.11
### Updated
 * Salesforce - Login Task - Removed the login task, all salesforce tasks now handle logging in automatically
 * Salesforce - Query - Error message returned by Salesforce are now logged
 * XML To CSV - Now supports XML documents using namespaces; provide the list of namespaces to use at the task level
 * XML To CSV - Default the separator to ',' and the delimiter to '"'

### Fixed
 * Sage 50 - Import Sales Orders - If Auto Create customer setting was enabled but customer already existed, would cause sales ledger data to be updated based on sales order address
 * Sage 50 - Import Invoices - If Auto Create customer setting was enabled but customer already existed, would cause sales ledger data to be updated based on invoice address

## Release 1.6.10
### Updated
 * Sage 50 - Import/Export Suppliers - Now support importing and exporting the Department field
 * Sage 50 - Import Sales Orders - Fixed issue with incorrect total net/total tax values when a discount is applied and the 'Discount By Unit Price' setting is enabled
 * Sage 50 - Import Invocies - Fixed issue with incorrect total net/total tax values when a discount is applied and the 'Discount By Unit Price' setting is enabled
 * Sage 50 - Import Purchase Orders - Fixed issue with incorrect total net/total tax values when a discount is applied and the 'Discount By Unit Price' setting is enabled
 * Sugar CRM - Upsert - Now supports setting relationships to existing records

### Fixed
 * Sage 200 - Import Stock Transactions - Resolved issue with stock lookup

## Release 1.6.9
### New
 * ConnectWise - Added a Update Invoice Payment task, documentation available on the Zynk API site (http://api.zynk.com)

### Updated
 * Sage 50 - Export Purchase Orders - Now include the Ref field in the exported data
 * Sage 50 - Email Statements - Added option to include/exclude accounts with a negative balance
 * Sage 200 - Import Sales Orders - Improved validation of the order item lines
 * Sage 200 - Import Sales Orders - Added validation of the currency and exchange rate
 * Sage 200 - Import Sales Orders - Now set the item line requested/promised delivery dates to the values at the item level in the XML (if provided)
 * Sage 200 - Import Purchase Orders - Improved validation of the order item lines
 * Sage 200 - Import Purchase Orders - Added validation of the currency and exchange rate
 * Sage 200 - Import Purchase Orders - Added support for setting the Project Analysis fields
 * Sage 200 - Import Purchase Orders - Now set the item line requested delivery date to the value at the item level in the XML (if provided)
 * Sage 200 - Export Purchase Orders - Now output the Project Analysis fields
 * Sugar CRM - All tasks - Updated to use the latest API version (V4_1)
 * Zynk - Export Truth Records - Added new/modified/all setting to the export

### Fixed
 * Sage 200 - Export Price Bands - Fixed issue with processing large OpLock values
 * Sage 200 - Export Stock Inventory - Fixed issue with processing large OpLock values
 * Sage 200 - Import Transactions - Fixed issue where journal debits/credits would fail validation due to no account reference being provided
 * Sage 200 - Import Purchase Orders - Fixed issue where additional charge codes would fail validation even if they did exist
 * Sage 200 - Import Purchase Orders - Now available for Sage 200 2013 (v9)
 * Sage 50 - Email Statements - Now set the transaction from date to the task last ran and the transaction to date to the current time

## Release 1.6.8
### New

### Updated
 * Sage 200 - Export Customers - Now export AccountOpened (date)
 * Sage 200 - Export Stock Records - Added option to export traceable items, was previously always exporting traceable items
 * Sage 200 - Import Sales Orders - Added option to choose printing of picking lists on imported orders (disabled, use the same setting as sage or enabled) - print picking lists setting must be enabled in Sage to be used on the import
 * Ebay Connector - Added option to connect to a sandbox account when logging in
 * Sage 50/200 - Import Tasks - Not providing an Id for a record in the input file is now treat as a warning rather than an error
 * Sage 50 - Import Goods Despatched Notes - Added support for despatching by customer order number

### Fixed

 * Sage 200 - Import Customers - The value in the Postal Name field on a delivery address was being deleted if not provided in the XML, will now keep the original value
 * Sage 200 - Import Customers - Update the description on delivery addresses
 * Sage 50 - Login - Fixed an issue where Zynk would crash on using a manual path if no companies are available from the drop down

## Release 1.6.7
### New
 * Added Help button which links to the help page for the selected task

### Updated
 * Task Library - Renamed Amazon MWS connector to Amazon Marketplace
 * Task Library - Removed 'Connect for' from all Sage connector names
 * Task Library - Renamed Sage 50 Payroll connector to Sage Payroll
 * Task Library - Split Database connector into separate connectors for each database type

### Fixed
 * Developer - Validate Resource - Fixed issue with a 403 Forbidden error
 * Sage 50 - Import Sales Orders - Auto create customer setting would always result in customers information being overwritten (if the customer existed already). will now only create an account if necessary
 * Sage 200 - Import Sales Orders - Issue with nominal being set on item lines if the use cc and dept option is enabled in Sage. will now use nominal if provided, otherwise, use sage 200 defaults

## Release 1.6.6
### New
 * Channel Advisor - Download Orders
 * Channel Advisor - Update Inventory
 * Coupa - Download Invoices
 * Coupa - Upload Invoice Payments
 * Coupa - Upload Suppliers

### Updated
 * Send Email - Added support for CC and BCC.

### Fixed
 * Sage 200 - Export Stock Records - Fixed issue with duplicate BOMs in output file
 * Auto Mapper - Parameter List - The ellipsis (...) button now scrolls with the list
