---
slug: send-email
redirect_from: "/article/224-send-email"
title: Send Email
---
This task will send an email using your own SMTP server or a [3rd Party SMTP Server](3rd-party-smtp-server) such as Mandrill.

## Settings
### Attachments
_Optional_  
The file or list of files to be attached to the email. TIP: You can also use the output from a [List Files](list-files) task to set the list of attachments dynamically.  Please bear in mind the sending rules of your email provider, you may not be able to send all attachment types. If the attachment type is not recognised by your computer, it may not be displayed correctly in the email, if at all. Should this happen, Zynk will log a debug message detailing the file(s) affected.

### Bcc
_Optional_  
The address to send a Bcc (blind carbon copy) of the email to. You can specify a list of email addresses if you would like to send the same email to multiple recipients. A list can be provided either as a comma separated list, or by chosing the ['List' data type](zynk-objects#list-data-type) and entering each address separately.

### Body
_Required_  
The content for the email. If the content is HTML, remember to set the HTML Body setting to True.

### Cc
_Optional_  
The address to send a Cc (carbon copy) of the email to. You can specify a list of email addresses if you would like to send the same email to multiple recipients. A list can be provided either as a comma separated list, or by chosing the ['List' data type](zynk-objects#list-data-type) and entering each address separately.

### From
_Required_  
The email address you are sending emails from e.g. me@mycompany.com

### HTML Body
_Required_  
Set to True if the body of the email is HTML.

### Subject
_Required_  
The subject text for the email.

### To
_Required_  
The address you are sending the email to. You can specify a list of email addresses if you would like to send the same email to multiple recipients. A list can be provided either as a comma separated list, or by chosing the ['List' data type](zynk-objects#list-data-type) and entering each address separately.

**TIP:** If this task is a sub-task of a repeater, you can use the context variables from the repeater task (e.g. 	`@Context.Current["Email_Address"]`) to dynamically set the address for each email.

### SMTP Connection
_Required_  
The SMTP Connection to send the emails from.  See the [Connecting to an SMTP Server](connecting-to-an-smtp-server) article here if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
An article on the use of this task is available [here](using-email-connector).

Sample input file for the email body, which contains a static message. Note that this is HTML, so the HTML Body setting will need to be set to True.

```html
<html>
    <head>
        <Style>
            * { font-family:verdana; }
            body { font-size: 75%; }
            h1 {font-size: 175%; font-weight:normal; font-family: Trebuchet MS}
        </Style>
    </head>


    <body>
        <p>Hi,</p>


        <p>Thanks for placing an order on our website, it is now being processed.</p>


        <p>Regards,<br/>The Zynk Team</p>
    </body>
</html>
```

Sample input file for the email body, which dynamically creates a personalised message by accessing the `Forename` and `Email_Address` current variables from a repeater task using razor. Note that this is HTML, so the HTML Body setting will need to be set to True.

```html
<html>
    <head>
        <Style>
            * { font-family:verdana; }
            body { font-size: 75%; }
            h1 {font-size: 175%; font-weight:normal; font-family: Trebuchet MS}
        </Style>
    </head>


    <body>
        <p>Hi @(Context.Current["Forename"]),</p>


        <p>We've created an account for you on our website, please log in using the username below and set your password.</p>


        <p>Username: @(Context.Current["Email_Address"])</p>


        <p>Regards,<br/>The Zynk Team</p>
    </body>
</html>
```
