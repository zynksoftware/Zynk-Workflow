---
slug: 3rd-party-smtp-server
redirect_from: "/article/225-3rd-party-smtp-services"
title: 3rd Party SMTP Server
---
If you plan on sending emails using Zynk and do not have an in-house SMTP server, there are a number of companies that offer excellent SMTP email sending services and most of them are compatible with Zynk.

## Mandrill
[Mandrill](http://www.mandrill.com/) is a transactional email product from the people who created MailChimp. Apps can use Mandrill to send automated one-to-one email, like password reminders, shopping-cart receipts, and notifications.

Mandrill also offers advanced tracking, easy-to-understand reports, and hundreds of template options that shouldn not be limited to bulk email newsletters. And it's built on MailChimp's proven email platform, which sends more than three billion emails a month.

It is quick to set up, has webhooks support, and high delivery rates. template options, tagging, and custom reports. Mandrill is the only transactional email product with a mobile app that allows you to monitor delivery and troubleshoot from wherever you are. You can send up to 12,000 emails per month absolutely free using their service after which they charge a very reasonable monthly fee.

### Configuring Zynk for use with Mandrill
It's easy to use the Email connector in Zynk to send emails using Mandrill - any Task that requires SMTP details to send emails such as the Sage connector tasks for Send Invoices task or the Send Statements just need to be populated with your Mandrill login details as shown in the example below:-

As you can see from screen shot below , all you need to send email via an SMTP server is an Email address and password along with an SMTP Server and SMTP Port, some SMTP services request that you use SSL - this is optional with Mandrill.

![Mandrill](http://www.zynk.com/images/zynk_integrations_mandrill.png)