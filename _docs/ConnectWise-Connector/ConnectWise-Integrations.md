---
slug: connectwise-integrations
redirect_from: "/article/183-introduction-to-the-connectwise-connector"
title: ConnectWise Integrations
---


**The ConnectWise Accounting API supports 3 types of exports and we have developed two workflows for use in Zynk and one more which is still in development.**



**Please note that the GL API requires a ConnectWise user license with Admin access. A license does not need to be purchased for the GL integration through the API, any Member ID and Password can be used.**



**ConnectWise Invoices to Sage Product Invoices**  
This Workflow will import any Unposted Invoices shown in the ConnectWise accounting interface which is located on the Other Accounting Interface tab and creates a Customer in Sage if they do not already exist and product invoices for each unposted invoice, it then updates ConnectWise to mark that batch of invoices as "posted". This integration will create Sage 50 product invoices which can then be posted to the Sales Ledger and Payments made against them



**ConnectWise Expenses to Sage Supplier and Purchase Invoices**  
This workflow will create each staff member (that has expenses) as a new supplier in Sage and their expenses are posted as unpaid Supplier Invoices against their individual supplier account, you then simply make a Supplier payment by cheque within Sage 50 when you pay their expenses to them. This is the recommended method for handling staff expenses in Sage 50. Please note that each staff "Member" record in ConnectWise must have the "Vendor Nbr" field set in order to be created as a supplier in Sage.



For further information on the specific Field mappings from ConnectWise to Sage along with the actual Workflows for use in Zynk please see the sub-pages in this section.

