---
slug: sftp-to-sage-50-integration
redirect_from: "/article/465-sftp-to-sage-50-integration"
title: SFTP to Sage 50 Integration
---
This tutorial details the basic principles when dealing with an integration between an **SFTP server** and **Sage**. This workflow will perform two basic tasks, which is the downloading orders from the SFTP in to Sage and then passing product information back up to the SFTP. We assume that the orders will be saved in a '/download' folder on the SFTP, and will be stored in the [Sage 50 UK Sales Order XML](sage-50-uk-sales-order-xml) format.

You can download a copy of the workflow from [here](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/SFTP%20to%20Sage%2050%20Integration/My%20Workflows). You will need to enter your SFTP details into each of the SFTP tasks in the workflow. See the link for each task for more information on how to do this.

## Download Orders From the SFTP - Phase 1
This part of the process will download all files from a 'download' folder on the SFTP, and import the orders contained within them into Sage 50. If the import was successful, the file on the SFTP will be moved to a 'processed' folder, to prevent the same orders from downloading again the next time the workflow runs. The process consists of the following tasks:

1. [SFTP Repeater](sftp-repeater) - This task will loop through all XML files in the 'download' folder on the SFTP, and run the sub-tasks below for each file.
    1. [Downloading Files with SFTP](downloading-files-with-sftp) - This task will download the current file from the SFTP and store it in the workflow's working directory. It does this by reading the name of the current file from the context variables from the above task.
    2. [Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk) - This task will import the orders contained in the file downloaded by the previous task into Sage 50. It will write out any failed or successful orders in to separate files. As before, the context variables from the SFTP Repeater task are used to get hold of the file currently being processed.
    3. [If File Exists](if-file-exists) - This task simply checks the size of the success file from the previous task to determine whether the order was imported successfully. If the order had not imported successfully, this file would not contain any data. If the file exceeds the minimum length, the sub-task below will run.	
        1. [Renaming Files with SFTP](renaming-files-with-sftp) - This task will move the successfully imported order file to the /download/processed folder. This will prevent the file being downloaded again the next time the workflow runs, as it will no longer exist in the /download folder. Alternatively, if there is no requirement to preserve the order files for traceability purposes, the [Deleting Files with SFTP](deleting-files-with-sftp) task could be used to delete the file from the SFTP.

## Upload Products to the SFTP - Phase 2
This part of the process will export any modified products from Sage 50, and upload them to the SFTP as a XML file in the Zynk XML Products format. The process consists of the following tasks:

1. [Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk) - This task will export modified product information from Sage 50 in Zynk XML format. The resulting file will be saved to the workflow's working directory
2. [Uploading Files with SFTP](uploading-files-with-sftp) - This task will upload the output file from the previous task to the '/upload' folder on the SFTP. It will append a timestamp on to the start of the file name, to prevent any previously uploaded product files from being overwritten.

#### Archive - Phase 3
This is the final task in the process, and will archive off all data that was used by the workflow process. This allows for traceability and will assist when debugging the workflow.

1. [Archive Workflow Data](archive-workflow-data) - This task will archive off all data in the root of the workflow's working directory.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.