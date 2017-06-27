---
slug: traffic-live-to-sage-50-uk-integration
redirect_from: "/article/459-traffic-live-to-sage-integration"
title: Traffic Live to Sage 50 UK Integration
---
We have established a partnership with Deltek who produce the client management system TrafficLIVE, which allows design and web studios to run and manage jobs, produce quotes and bills, automatically integrating the associated billing information into Sage 50 UK.

We don't manage the scripts that generate the data for this integration, this is done by Deltek. Any custom requirements (anything outside the detail of this article) will need to be raised with Deltek.

This integration will export invoices from **TrafficLIVE** and import them into **Sage 50 UK** as Sales Invoices. You can find a sample workflow and a sample file on our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Traffic%20Live%20Integration).

Instructions on how to set up your TrafficLIVE system can be found 		[here](http://trafficlive.screenstepslive.com/s/2523/m/userguide/l/54862-fully-automated-posting-to-sage-line-50-sales-ledger-posting#), if you have any queries on this please contact the TrafficLIVE support team on 0800 880 3002.

## Workflow Overview
The following sections provide an overview of the tasks used by the TrafficLIVE To Sage 50 UK Integration and explain each task's function within the Workflow process.

#### Download Transactions - Phase 1
This part of the process will download and import your invoices from TrafficLIVE in to Sage 50 UK.

[HTTP Task](http-task) - Download Transactions

This task will download the transactions from TrafficLIVE and store them in an XML file.

 * **Method** - Make sure that this is set to 'GET' so we can download the data.
 * **Output File** - Here you can specify the name of the XML file that you are storing the TrafficLIVE invoices in.
 * **Password** - This is configured at a Variable level. When in the workflow if you go to 'Properties and then 'Variables' you will see a variable with the key 'PASSWORD', populate this with your API token generated from TrafficLIVE.
 * **URL** - This is provided by TrafficLIVE and is authenticated based on your username an password.
 * **Username** - This is the email address you used when you signed up for TrafficLIVE and is configured at a Variable level. When in the workflow if you go to 'Properties' and then 'Variables' you will see a variable with the key 'USERNAME', populate this with your TrafficLIVE email.

[Importing Transactions into Sage 50 UK](importing-transactions-into-sage-50-uk)

This task will import your TrafficLIVE in to Sage 50 UK as Sales Invoices.

 * **Fail File** This will be the destination for any failed transactions.
 * **Input File** This will be the Output File from the previous task and the file that is imported in to Sage 50 UK.
 * **Success File** This will be the destination of any successful transactions.

[HTTP Task](http-task) - Notify Successful Transactions

This task will notify any successful transactions that have been imported from TrafficLIVE.

 * **Header Values**This needs to be set to the content type of the file being sent to TrafficLIVE.
 * **Input File**This will need to be set the Success File from the previous task.
 * **Method**This will need to be set to 'POST' as this is part of the notify process.
 * **Password**This is configured at a Variable level. When in the workflow if you go to 'Properties and then 'Variables' you will see a variable with the key 'PASSWORD', populate this with your API token generated from TrafficLIVE.
 * **URL**This is provided by TrafficLIVE and is authenticated based on your username an password.
 * **Username**This is the email address you used when you signed up for TrafficLIVE and is configured at a Variable level. When in the workflow if you go to 'Properties' and then 'Variables' you will see a variable with the key 'USERNAME', populate this with your TrafficLIVE email.

[HTTP Task](http-task) - Notify Failed Transactions

This task will notify any failed transactions that have not been imported from TrafficLIVE.

 * **Header Values** - This needs to be set to the content type of the file being sent to TrafficLIVE.
 * **Input File** - This will need to be set the Success File from the previous task.
 * **Method** - This will need to be set to 'POST' as this is part of the notify process.
 * **Password** - This is configured at a Variable level. When in the workflow if you go to 'Properties and then 'Variables' you will see a variable with the key 'PASSWORD', populate this with your API token generated from TrafficLIVE.
 * **URL** - This is provided by TrafficLIVE and is authenticated based on your username an password.
 * **Username** - This is the email address you used when you signed up for TrafficLIVE and is configured at a Variable level. When in the workflow if you go to 'Properties' and then 'Variables' you will see a variable with the key 'USERNAME', populate this with your TrafficLIVE email.

#### Archive - Phase 2
This part of the process will archive off any data used in the workflow.

[Archive Workflow Data](archive-workflow-data)

 * **Archive Folder**Specify this to folder that you want to archive your data to.

## Configuring the Workflow

The following points detail how to configure the 		[TrafficLIVE Workflow](https://raw.githubusercontent.com/zynksoftware/samples/master/Integration%20Samples/Traffic%20Live%20Integration/My%20Workflows/TrafficLIVE%20-%20Sage%2050%20UK.wkf), this involves entering the TrafficLIVE details and configuring the Sage 50 UK connection to use.

 * Copy the Workflow to the My Workflows directory in Zynk: C:\ProgramData\Zynk Software\Zynk\2.0\My Workflows
 * Open Zynk and then double click the Workflow to edit it  
[![Open TrafficLIVE to Sage 50 Workflow](http://www.zynk.com/images/v2/trafficlive/open-workflow.png)](http://www.zynk.com/images/v2/trafficlive/open-workflow.png)
 * Select the 'Import Transactions' task from the Tasks that make up the Workflow to view the Task Properties		  
[![Select Import Transactions task in TrafficLIVE to Sage 50 Workflow](http://www.zynk.com/images/v2/trafficlive/select-import-transactions.png)](http://www.zynk.com/images/v2/trafficlive/select-import-transactions.png)
 * Select the Sage 50 Connection Property and click the button to select the Sage 50 UK company to connect to  
[![Select Sage 50 UK Connection on Import Transactions task in TrafficLIVE to Sage 50 Workflow](http://www.zynk.com/images/v2/trafficlive/select-connection.png)](http://www.zynk.com/images/v2/trafficlive/select-connection.png)
 * You may need to create a new Sage 50 Connection if this is a fresh install of Zynk  
[![Create a New Sage 50 UK Connection in TrafficLIVE to Sage 50 Workflow](http://www.zynk.com/images/v2/trafficlive/new-connection.png)](http://www.zynk.com/images/v2/trafficlive/new-connection.png)
 * You can find more information on [Connecting to Sage 50 UK](connecting-to-sage-50-uk) here.
 * Next you will need to edit the Workflow Properties to enter the TrafficLIVE USERNAME and PASSWORD  
[![Click Workflow Properties Tab](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-1.png)](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-1.png)[![Click Variables on the Properties Tab](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-2.png)](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-2.png)
 * The USERNAME will be the email address used to log into TrafficLIVE  
[![Edit the USERNAME Workflow Variable, populating with the TrafficLIVE email address](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-username.png)](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-username.png)
 * The PASSWORD will be the API Key that was generated from TrafficLIVE  
[![Edit the PASSWORD Workflow Variable, populating with the API Key generated on TrafficLIVE](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-password.png)](http://www.zynk.com/images/v2/trafficlive/edit-workflow-properties-password.png)
 * Now you can schedule the Workflow to run at the desired frequency. We don't advise scheduling Sage 50 UK integrations any more frequently than once every 15 minutes due to the impact this can have on performance in the application.
 * If the Sage 50 User being used by Zynk to connect up to Sage is already in use then the integration will not be able to run. Whenever any maintenance operations need to be carried out in Sage (backup, restore etc.), you should ensure that the Zynk schedule is disabled prior to this. You can find more information on Scheduling Workflows and disabling Zynk schedules here.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.
