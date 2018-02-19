---
slug: connectwise-integrations-frequently-asked-questions
redirect_from: "/article/184-connectwise-connector-frequently-asked-questions"
title: ConnectWise Integrations Frequently Asked Questions
---


**Q: Where can I see the data that will be downloaded from ConnectWise to Sage?**



Click on the Other section then choose Accounting Interface and you will see some tabs shoing Unposted Invoices, Unposted Expenses and Unposted Procurement (Invoices from Purchase Orders)



**Q: How are Invoices downloaded from ConnectWise to Sage?**  
Invoices must first be closed in ConnectWise before they appear in the Unposted Invoices area of the Accounting Interface they are downloaded, and the link will download each ConnectWise invoice as a Sage Product Invoice, using the SKU from the product record in ConnectWise, where a SKU does not exist the system will default to S1 - this has an impact if you are using Agreement invoicing in ConnectWise as these items have no SKU.



**Q: How are Expenses downloaded from ConnectWise to Sage?**  
The link will download all Unposted Expenses from the Accounting Interface as Purchase Invoices, you must however, give each user their own Vendor Code (Account reference) in ConnectWise so that the system can create a Supplier account in Sage. Then all you do is make a Supplier Payment manually to each of your employees Supplier accounts to settle their expenses at the end of the month.



**Q: How is Procurement downloaded from ConnectWise to Sage?**  
Procurement (Purchase Orders) are shown in the Unposted Procurement section in the ConnectWise Accounting Interface. They are transferred into Sage as Purchase Invoices against the related supplier account. Supplier accounts in ConnectWise must have an Account reference set so they can be downloaded into Sage



**Q: How does the link support Agreement invoicing?**  
Agreement invoices in ConnectWise do not hold a SKU code so the import into Sage 50 will use an S1 stock code in Sage 50 to represent these agreement lines. S1 stock code is a non-stock item and does not update any stock.



**Q: What if the integration does not work the way I want it to work?**  
See How do I customise the Integration



**Q: The standard mappings don not suit my business so I need the integration customising to my requirements - is this possible?**  
Yes, we can customise the mappings for you - this work is billed at our standard hourly rate.



**Q: How do I customise the integration?**  
The integration makes calls to the ConnectWise API and data is fetched from the ConnectWise API in XML format, we then use a standard XSLT file to transform the ConnectWise data into our own Sage XML format - this XSLT mappings file is fixed but it can be customised by our developers (or your own developers) - all customisation work is billed at our standard hourly rate.



**Q: I need some additional information bringing down from ConnectWise into Sage**  
ConnectWise only exports a set number of fields so there are some limitations as to what we can bring into Sage



**Q: What are the mappings on Product invoices?**  
Please see this page [http://tinyurl.com/72tup4t](http://tinyurl.com/72tup4t)



**Q: Can I get a trial of Zynk for ConnectWise?**  
No, due to the time for setup and configuration we do not provide a trial of Zynk for ConnectWise.

