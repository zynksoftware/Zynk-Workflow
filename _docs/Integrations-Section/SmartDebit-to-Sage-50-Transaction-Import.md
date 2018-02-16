---
slug: smartdebit-to-sage-50-transaction-import
redirect_from: "/article/455-smartdebit-to-sage-50-transaction-import"
title: SmartDebit to Sage 50 Transaction Import
---
The SmartDebit to Sage 50 integration allows you to download all new direct debits taken through SmartDebit and import into Sage 50 as either Sales Receipts or Bank Receipts.  The integration allows you to customise the import, specifying the Bank account code, Nominal code, Department, Account reference and Transaction references to use for transactions.  The integration will download all SmartDebit transactions for the specified period and import them as Sales Receipts against the account reference held in SmartDebit.

## Getting Started
To use the integration you will need to have Sage 50 and Zynk installed, a valid SmartDebit API username, password and PSLID.  If you require API details please contact SmartDebit directly as we are unable to provide direct support of their API.

If you do not have any SmartDebit API credentials, you can contact SmartDebit by emailing support@smartdebit.com

You can [register for a trial of Zynk here](http://zynk.com/download-trial/).

To configure the integration you will need to download the SmartDebit to Sage 50 Workflow, which can be [found here](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/SmartDebit%20to%20Sage%2050/My%20Workflows).  You can also find a copy of the workflow in Zynk under the Workflow Templates section.

## Connecting to SmartDebit
Once you have installed Zynk and the workflow you will need to configure the tasks to connect to your systems.  Open the workflow in Zynk and select the Download Direct Debits tasks, then follow the instructions below to create a new connection to Smart Debit.

1. Click the Connection setting, then open up the drop down.
2. Click the New button.
3. In the window that appears, click Next, then fill in your Username, Password and PSLID in the boxes provided. Click Finish to save the connection to Smart  Debit.
4. Select the newly created connection from the Connection setting drop down.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09f1dc6979143615648e2/file-yVXFFsTb0v.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09f1dc6979143615648e2/file-yVXFFsTb0v.png)

You should also set the Download Date setting on the Download Direct Debits task to when you want to start downloading transactions from.

## Connecting to Sage 50
To connect to Sage 50 simply run the workflow, you will be prompted to choose your company and enter a username and password.  We would recommend you create a new user for Zynk to connect to Sage so you can run the integration while you are logged in to Sage.

## Customising the Mapping
You can customise the following fields within the integration; these can either be a literal piece of text e.g. setting your Bank code to '1200', or a field from the SmartDebit direct debit feed. To change the mappings, open the workflow in Zynk, highlight the Auto Mapper task, and click the edit button (ellipsis) by Mapping. Setting the Value column in the Parameters table will allow you to change the mapping as required.  Note, you can only customise basic field mappings.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a0539033603f7da37028/file-qVqwNiCnmm.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a0539033603f7da37028/file-qVqwNiCnmm.png)

Make sure all these parameters are specified in the Auto Mapper configuration.

## Customisable Fields
| Field Name | Description | Example / Default |
| --- | --- | --- |
| TransactionType |Type to import, either SalesReceipt or BankReceipt |SalesReceipt |
| BankCode | The bank reference to use for receipts, must exist in Sage | 1200 |
| NominalCode | Nominal code for transactions | 4000 |
| Department | Department for transactions| |
| TaxCode | Tax code for transactions| |
| AccountReference | The account reference for receipts, must exist in Sage | payer_reference |
| Reference | The reference to use for receipts |reference_number |
| PaymentReference | The external reference to use for receipts| |
| Details | The details to use for receipts | |

## Available SmartDebit Fields
| FieldName | Example |
| --- | --- |
| company_name | Internetware Limited |
| title | Mr |
| first_name | Andrew |
| last_name | Snape |
| frequency_type | M |
| start_date | 2010-11-14T00:00:00Z |
| reference_number | INW000000 |
| payer_reference | INT001 |
| address_1 | 6-8 Charlotte Square |
| address_2 | |
| town | Newcastle |
| country | UnitedKingdom |
| postcode | NE14XF |
| email_address | support@internetware.co.uk |
| default_amount | 1000 |
| first_amount | 1000 |

# Testing the Integration
We would advise testing the integration against a copy of your Sage data before running against your live accounts.  You can do this either by setting up a second company within Sage 50, or ensuring you have taken a recent backup and can run a restore if required.

The integration downloads transactions based on the date of the direct debits; you can control when the integration will start, or reset the integration if you are testing, by changing the Download Date setting under the Download Direct Debits task.

## Reporting
Zynk can optionally send you an import report via email, summarising successfully imported transactions as well as any failed transactions (due to invalid or insufficient information) along with the reason for failure. In order to receive the report you will need to click on the checkbox to enable the task in the workflow, then specify the SMTP details for your own Email, by following the instructions below:

1. Click the SMTP Connection setting, then open up the drop down.
2. Click the New button.
3. In the window that appears, click Next, then enter your SMTP details into the boxes provided. Click Finish to save the connection to the SMTP server.
4. Select the newly created connection from the  SMTP Connection setting drop down.

Any failed transactions in the report will need to be entered manually into Sage 50.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a0f99033603f7da3702b/file-kq2DwEOuej.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a0f99033603f7da3702b/file-kq2DwEOuej.png)

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279. Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.