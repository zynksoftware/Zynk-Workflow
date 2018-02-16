---
slug: troubleshooting-the-sage-50-uk-connector
redirect_from: "/article/702-troubleshooting-the-sage-50-uk-connector"
title: Troubleshooting the Sage 50 UK Connector
---
## What does the Exclusive Mode error mean?
If you receive the below error in Zynk it generally means that a Sage back up is taking place at the time of the workflow run:

Program is in exclusive mode. Logon cannot proceed   
at System.RuntimeType.ForwardCallToInvokeMember(String memberName,   
BindingFlags flags, Object target, Int32[] aWrapperTypes, MessageData&   
msgData) at SageDataObject120.IWorkSpace.Connect(String Path, String Usr,   
String Psw, String Unique) at Zynk.Sage.Sage50.Sage50Base.Connect()

Please wait for the back up to complete before trying to run Zynk again.

## What do I do if my Sage 50 information changes?
If you have changed the location, version or login information (username or password) of your Sage 50 data you will have to update these settings in your Workflow. The process to update your connection details varies depending on the version of Zynk you are using. You can find the version number in the application under Help > About.

### Zynk V2.1+
Zynk will automatically detect the version of Sage you have installed, so you only need to update the connection if your username, password or data location has changed. Refer to the instructions for Zynk v2.0 - 2.0.3 for how to do this.

### Zynk V2.0 - 2.0.3
1. Click the 'Connection Manager' button on the main toolbar.
2. Double click on the Sage 50 connection you need to update.
3. Follow the instructions on [Connecting to Sage 50 UK](connecting-to-sage-50-uk) to update your Sage 50 details.

### Zynk V1.X
Click the 'Workflow Properties' tab and then click the button next to the 'Variables' to edit the list of 'Workflow Variables', select the following variable names from your Workflows Variables and press the 'Delete' key on your keyboard for each one :

 * SAGE50_BUGFIX
 * SAGE50_DATAPATH
 * SAGE50_MAJOR
 * SAGE50_MINOR
 * SAGE50_NAME
 * SAGE50_USERNAME
 * SAGE50_PASSWORD

Once you have deleted all of the above variables, if you Save your workflow and then select 'Run Workflow' you will be prompted to re enter your Sage login information once the Workflow reaches the first Sage 50 task.