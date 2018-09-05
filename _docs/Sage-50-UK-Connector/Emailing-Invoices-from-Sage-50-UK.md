---
slug: emailing-invoices-from-sage-50-uk
redirect_from: "/article/392-emailing-invoices-from-sage-50-uk"
title: Emailing Invoices from Sage 50 UK
---
This task will generate a PDF invoice for all invoices that have not yet been printed, and send it to the email address on the customer account as an attachment, via an SMTP server.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### SMTP Connection
_Required_  
The connection for the SMTP server to use.  See the [Connecting to an SMTP Server](connecting-to-an-smtp-server) article if you require more information on how to create/manage connections.

### Body
_Required_  
The content for the email. If the body is in HTML, be sure to set 'HTML Body' to true.

### From
_Required_  
The email address the emails will appear from (e.g. noreply@mycompany.com)

### HTML Body
_Required_  
Set to true if the body of the emails are HTML

### Strong Validation
_Required_  
Set to true to only send the email if the customer's email address was successfully validated against the destination SMTP server, or false to still send the email if it was not possible to validate the email addresses against the server. This setting only takes effect when the 'Validate Against SMTP Server' setting is set to true.

### Subject
_Required_  
The subject for the emails

### Validate Against SMTP Server
_Required_  
Set to true to validate the customer email addresses against the destination SMTP server before trying to send the email, or false to perform only basic validation on the format of the email address.

### Send Failure Notification
_Required_  
Set to true if you would like to be sent a notification if an invoice could not be sent due to an invalid customer email address or an email send error. The notification includes the invoice as an attachment.

### Send To
_Optional_  
The email address to send the failure notification email to. You can specify a list of email addresses if you would like to send the same email to multiple recipients. A list can be provided either as a comma separated list, or by chosing the ['List' data type](zynk-objects#list-data-type) and entering each address separately.

### Add Background
_Required_  
Set to true to add a background to the invoices generated. For example, this could be used to include a letterhead or watermark in the invoices.

### Background File
_Optional_  
The file to use as the background to the invoices generated.

### Report File
_Required_  
The Sage .report/.layout file to use to generate the invoices (e.g. C:\ProgramData\Sage\Accounts\2013\Company.000\Layouts\INVPRCA4.layout)

### Use Test Mode
_Required_  
Set to true to send the invoices to the 'From' address instead of the customer's address, and to prevent the printed and emailed flags being updated in Sage. This should be used during testing to prevent customers receiving the emails, and to allow you to view them for yourself.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Sending Invoices and Statements from Sage 50](sending-invoices-and-statements-from-sage-50) article.

