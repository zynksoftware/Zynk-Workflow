---
slug: email-repeater
redirect_from: "/article/223-email-repeater"
title: Email Repeater
---
This task will query an email account and run each of the sub-tasks for each inbound email. Currently supports POP3 mail accounts only.

## Settings
### Attachments Directory
_Optional_  
Enter the directory to save email attachments to. The attachments for each email will be saved to a sub directory based on the message ID. Leave blank to not download attachments.

### Delete Attachments
_Optional_  
Set to True delete all attachments downloaded to the Attachments Directory once the task has finished. The attachments won't be deleted from the server.

### Delete Messages
_Required_  
Set to True to delete the messages from the server once they have been downloaded.

### POP3 Connection
_Required_  
The POP3 Connection to download emails from. See the [Connecting to a POP3 Server](connecting-to-a-pop3-server) article here if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
The following variables are available to the sub-tasks. To use these variables, reference them in templates as `@Context.Current["From"]`, or within sub-task settings using the Razor option.

 * **Id** - The Message-Id of the email.
 * **To** - The to address.
 * **From** - The from address.
 * **FromName** - The name of the sender.
 * **Cc** - The Cc address(es).
 * **Bcc** - The Bcc address(es).
 * **DateSent** - The date the email was sent.
 * **Date** - The date the email was received.
 * **Subject** - The subject of the email.
 * **AttachmentDirectory** - The directory the attachments were saved to.
 * **BodyText** - The email body, in text format.
 * **BodyTextHtml** - The email body, in HTML format.