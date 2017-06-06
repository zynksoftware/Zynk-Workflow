---
slug: creating-your-first-workflow
redirect_from: "/article/619-creating-your-first-workflow"
title: Creating Your First Workflow
---
To start with we are going to create a very simple workflow to demonstrate how Zynk works and implement what would normally take several hours programming in just a couple of minutes.

1. Open Zynk and click on the New Workflow button or choose File > New from the main menu
2. You should now see the Task Library pane displayed.
3. Navigate down to the Web Library and then Double-click (or Drag and drop) the HTTP Task to copy that task into the Tasks List
4. Click on the HTTP Task in the Tasks List and change the following settings
 1. Set the URL property to [http://www.zynk.com](http://www.zynk.com/) (or another address if you wish)
 2. Set the Output File property to c:\website.html
5. Locate the User Interface Library in the Task Library pane and add drag and drop the Display Last Output task to the Task Builder
6. Click on the Save button and enter the name *Tutorial 1* for the name of the Workflow and click Save
7. Click on the Run Workflow button
8. You should now see the Zynk website open in a browser - but what we have actually done is "copied" that entire page to our C drive
9. Look in the My Computer > C drive and you find a file called website.html has been created

Congratulations, you have just created your first Zynk Workflow!  
 
What Next?

Why not try rendering the HTML page to a PDF using the HTML to PDF Task and then send the PDF to yourself via email - You'll need to use the PDF Library and the Email Library to accomplish this.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b08b76c697914361564852/file-KE1eTQbagZ.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b08b76c697914361564852/file-KE1eTQbagZ.png)