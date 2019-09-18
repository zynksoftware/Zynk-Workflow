---
slug: re-installing-zynk
redirect_from: "/article/66-re-installing-zynk"
title: Reinstalling Zynk
---
If you are moving Zynk from one machine to another, you will need to go to Help > About within Zynk and email the exact version to us at [support@zynk.com](mailto:support@zynk.com) so we are able to send you the correct .exe file for re-install.

+ The Zynk programdata will need to be copied to the new server. 
+ Ensure the workflows are not currently running and are not scheduled to start until the migration is complete


<!-- [Running a Workflow](../using-zynk-section/running-a-workflow) -->
<!-- [Managing Workflow Schedules](scheduling-a-workflow#managingschedules) -->

Depending on the version of Windows you are running on this can be found in one of the following locations:

In Windows XP or earlier: 

**C:\Documents and Settings\All Users\Application Data\Zynk Software\Zynk\2.0**

In Windows Vista or Later: 

**C:\ProgramData\Zynk Software\Zynk\2.0**

After reinstalling, replace the newly created 2.0 folder with the data copied from your existing Zynk data directory.

When you are ready to start using Zynk you will need to access Zynk on the old machine and on the top bar select Tools --> License Manager where you can deactivate the license from that machine for reactivation on the new installation. If you are unable to manually deactivate for any reason please contact support@zynk.com so we can do this for you.

In addition for connections that rely on a specific data path (For example, Sage 50 UK and US) these connections will need to be reconfigured to use the new data path.

**Please note that if Zynk Software did not build the integration then you should contact your developers to ensure all data/files are copied from and to the relevant locations.**
