---
slug: sending-invoices-and-statements-from-sage-50
redirect_from: "/article/645-sending-invoices-statements-from-sage-50"
title: Sending Invoices and Statements from Sage 50
---
 In this tutorial, we demonstrate how to use the [Email Invoices](emailing-invoices-from-sage-50-uk) and [Email Statements](emailing-statements-from-sage-50-uk) tasks, to automate the process of sending invoices/statements to your customers in Sage. Note that we only adjust some ofthe settings for these tasks in this tutorial, and leave the rest at their default values. Refer to the links above for anexplanation of all of the settings.        

## Email Invoices
This task will generate a PDF invoice for all invoices that have not yet been printed, and send it to the email address on            the customer account as an attachment, via an SMTP server. The basic settings are as follows:           

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b45f45c697914361565aaa/file-szEKvzY33f.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b45f45c697914361565aaa/file-szEKvzY33f.png)

 * **Body** - Enter the body of the email (e.g. 'Please find your latest invoice attached').
 * **From** - The email address that will be seen by the customers receiving an invoice in the 'From' field. Depending            on your SMTP server, you may be required to use a specific address.
 * **Subject** - Enter the subject for the emails (e.g. 'Your Invoice From Zynk Software Ltd').
 * **Report File** - Enter the Sage .report/.layout file to use to generate the invoices (e.g. C:\ProgramData\Sage\Accounts\2013\Company.000\Layouts\INVPRCA4.layout).
 * **Sage 50 Connection** - Select the Sage 50 company to connect to and generate invoices from.
 * **SMTP Connection** - Select the SMTP server to send the emails from.
 * **Test Mode** - Set to true to send the invoices to the 'From' address instead of the customer's address. This should            be used during testing to prevent customers receiving the emails, and to allow you to view them for yourself.

## Email Statements
This task will generate a PDF statement for customers that have a non zero balance on their account, and send it to the email            address on their account as an attachment, via an SMTP server. The basic settings are as follows:            
[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b45f9d9033603f7da3836e/file-HtnBxQRe8e.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b45f9d9033603f7da3836e/file-HtnBxQRe8e.png)

 * **Body** - Enter the body of the email (e.g. 'Please find your latest statement attached').
 * **From** - The email address that will be seen by the customers receiving a statement in the 'From' field. Depending            on your SMTP server, you may be required to use a specific address.
 * **Subject** - Enter the subject for the emails (e.g. 'Your Statement From Zynk Software Ltd').
 * **Report File** - Enter the Sage .report/.layout file to use to generate the invoices (e.g. C:\ProgramData\Sage\Accounts\2013\Company.000\Layouts\EMASTOS.layout).
 * **Sage 50 Connection** - Select the Sage 50 company to connect to and generate invoices from.
 * **SMTP Connection** - Select the SMTP server to send the emails from
 * **Test Mode** - Set to true to send the statements to the 'From' address instead of the customer's address. This            should be used during testing to prevent customers receiving the emails, and to allow you to view them for yourself.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com            or via telephone on 0191 303 7279. Please note, as stated on the Auto Mapper task we do not support any changes            to XSLT.