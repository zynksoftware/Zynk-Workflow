---
slug: using-ftp-repeater
redirect_from: "/article/626-using-ftp-repeater"
title: Using FTP Repeater
---
The FTP Repeater task will allow you to run a series of sub-tasks against all the files in the directory on the remote server. This tutorial will show you how to use the context variables within the repeater, and to download and remove files fromthe remote server.  You can download the [sample workflow here](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples),or build the workflow manually using the instructions below.        

The repeater could be used if you have a system that outputs data to an FTP site e.g. new orders are written out in XML format.  Zynk can list all the files in the directory, and for each of files run any required sub-tasks e.g. download            the file and import into another system.

To use the sample workflow you will need to have access to an FTP server, and have the required credentials to hand.  Edit the workflow variables, and set your details for `FTP_SERVER`, `FTP_USERNAME`, `FTP_PASSWORD` and `FTP_DIRECTORY`.

The first task in the repeater will list all the context variables available to the sub-tasks, it will write a line out for each file found in the directory.  Using the example of download orders from a site, the second and third tasks in the repeater (you will have to enable these) will download any files as orders.xml, and remove the file from the FTP site.  Note enabling the delete task will remove files stored on  your FTP site, make sure you are using this on a test environment.

## Building the Workflow
1. Open Zynk and click on the New Workflow button or choose File > New from the main menu
2. Optionally add workflow variables for `FTP_SERVER`, `FTP_USERNAME`, `FTP_PASSWORD` and `FTP_DIRECTORY`
3. You should now see the Task Library pane displayed, Click on the FTP Library and then Double-click (or Drag and drop) the FTP Repeater to copy that task into the Tasks List
4. Set the Server, Username, Password and Directory values, optionally using the variables if you configured these in step 2
5. Locate the User Interface Library in the Task Library pane and add the Log Info Message task to the Task Builder
6. Set the Input to the code below, ensuring to select Use Razor
7. Locate the FTP Library in the Task Library pane and add the FTP Download task to the Task Builder
8. Set the details as per step 4, and set the File Name to @Context.Current["Name"], using Razor.  Set the Output File to orders.xml
9. Locate the FTP Library in the Task Library pane and add the FTP Delete task to the Task Builder
10. Set the details as per step 4, and set the Filename to @Context.Current["Name"], using Razor

Code for Log Info Message Input

```cs   
@{
    Response.Write(string.Format("{0} - {1} - {2} - {3} - {4}",
    Context.Current["Name"],
    Context.Current["Extension"],
    Context.Current["NameWithoutExtension"],
    Context.Current["Directory"],
    Context.Current["Server"]
    ));
}
```