---
slug: backing-up-your-data
redirect_from: "/article/52-backing-up-your-data"
title: Backing Up Your Data
---
It is good practice to take backups of your data on a regular basis. Zynk has built in tools which will allow you to do this.

## Creating a Backup
To create a backup, click on File, and then click Backup. You will then see a message like the one below.

[![Zynk Backup](http://www.zynk.com/images/v2/zynk_backup1.png)](http://www.zynk.com/images/v2/zynk_backup1.png)

You can use the 'Browse' button to change the save location of the backup file, if required. Then, click the 'Ok' button to create the backup file. You should then get a message confirming that the backup file has been successfully created.

## Scheduling Backups
It is possible to create a workflow which will run backups automatically according to a schedule. To do this, follow the steps below.

1. Create a new workflow.
2. Add the 'Create Backup' task from the 'Zynk' task library to the workflow.
3. Set up the 'Create Backup' task. You can refer to Zynk Core Library for guidance on how to do this.
4. Click on the 'Schedule' button on the toolbar.
5. Set the times you want the backup to run. You can refer to [Scheduling a Workflow](scheduling-a-workflow) for guidance on how to do this.
6. Save the workflow.

## Restoring Your Data From a Backup
If you happen to have lost any of your workflows or other data, you can restore them using a backup file you had created earlier. Please bear in mind that the workflows and data you currently have will be overwritten by their counterparts from the backup file. Any workflows or data that you currently have which were not included in the backup will be preserved.

To restore your data from a backup, click on File, and then click Restore. You will then see a message like the one below.

[![Zynk Restore](http://www.zynk.com/images/v2/zynk_restore_1.png)](http://www.zynk.com/images/v2/zynk_restore_1.png)

Use the 'Browse' button to locate the backup file, and then, click the 'Ok' button. You will then get a message asking you to confirm you want to overwrite any existing data. Click the 'Ok' button to confirm that you want restore. If the restore was successful, you will get a confirmation message. Click the 'Ok' button, and Zynk will restart with you backup data restored.