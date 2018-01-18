---
slug: scheduling-a-workflow
redirect_from: "/article/71-scheduling-a-workflow"
title: Scheduling a Workflow
---
You can easily schedule any Workflow to run at a specific time and then repeat every 15 minutes, hour, day, week or month. The scheduler uses the built in Windows scheduling service to execute Zynk at the times you specify.

## Setting up a Schedule
1 - Click on the Scheduler button on the Workflow builder, and select the 'Run on a schedule' option. This will create a default schedule which will run the workflow every 15 minutes.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09937c6979143615648c5/file-rFicZN74r1.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09937c6979143615648c5/file-rFicZN74r1.png)

2 - To change the settings of the schedule, click on the 'Edit' button.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09941c6979143615648c7/file-jgQtCp8Eap.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09941c6979143615648c7/file-jgQtCp8Eap.png)

3 - Click on the 'Triggers' tab, and then click 'Edit'.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09958c6979143615648c8/file-RMUZD5hd0C.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09958c6979143615648c8/file-RMUZD5hd0C.png)

4 - Configure the settings for when the schedule should run, then click 'Ok'. You can specify whether the schedule should run once, daily, weekly or monthly, what time it should start, and how often the task should be repeated. By default the schedule runs daily and repeats every 15 minutes from midnight.

## Managing Schedules
Scheduled Workflows can be managed from the Task Scheduler within Windows (please note that this may appear as Scheduled Tasks in earlier versions of Windows).

1 - Launch the Task Scheduler window

a. either by searching the Windows start menu   
[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56976c6979156e4f1f452/file-Q0TepJYsUF.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56976c6979156e4f1f452/file-Q0TepJYsUF.png)

b. or by clicking Run and typing 'taskschd.msc' and clicking Ok   
[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56a40c6979156e4f1f458/file-y50VFhWSha.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56a40c6979156e4f1f458/file-y50VFhWSha.png)

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56aeec6979156e4f1f45a/file-aiF2Kjw1NA.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56aeec6979156e4f1f45a/file-aiF2Kjw1NA.png)

2 - Find the Zynk Workflow schedule that you would like to manage (the scheduled task name will match the Workflow name in Zynk).

a. Scheduled tasks created in the most recent version of Zynk (2.0 or later) will be organised under a 'Zynk' folder in the 'Task Scheduler Library'   
[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56c46c6979156e4f1f46b/file-gxj0WyWNi8.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c56c46c6979156e4f1f46b/file-gxj0WyWNi8.png)

b. Scheduled tasks created in earlier versions of Zynk (1.0) will appear under the 'Task Scheduler Library'   
[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c571b9c6979156e4f1f488/file-W1MXuE5Ccb.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/57c571b9c6979156e4f1f488/file-W1MXuE5Ccb.png)

3 - Once you have identified the scheduled Zynk Workflow that you would like to manage, right click the entry in the 'Task Scheduler', from here you can:

a. Disable a schedule so that the Workflow will not automatically run until re-enabled.

b. Enable a schedule that has been previously Disabled.

c. Delete a schedule so that the Zynk Workflow will never run automatically.

## Errors
In some cases you may see the following error message appear in the Error tab after clicking the OK button when configuring the schedule:

Access is denied. (Exception from HRESULT: 0x80070005 (E\_ACCESSDENIED))

If this happens, try closing Zynk, then right click on the Zynk application in the Start menu, and click **Run as administrator**. Then try setting the schedule again.

## Advanced Customisation of Scheduled Tasks
If you need to customise the schedule further or specify a user account for the schedule to run under, you can edit the schedule directly in the Windows Task Scheduler by clicking on **Start > All Programs > Accessories > System Tools > Task Scheduler.** Any workflows which have been scheduled will appear under the **Task Scheduler Library** > **Zynk**, with the workflow's name as the title. Double click on the appropriate entry to edit the schedule.
