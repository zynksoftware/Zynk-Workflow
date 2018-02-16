---
slug: using-ui-library
redirect_from: "/article/636-using-ui-library"
title: Using UI Library
---
 This article will step you through how to use the four tasks in the User Interface folder in the Zynk Task Library. Please note, these tasks are generally used for debugging purposes and should not be used when running a scheduled task.        

## Display Last Output
This example will show you running an export from Sage 50 and displaying the result. The Display Last Output task will open            the file exported from Sage 50 for you to peruse. As you can see, I have set up a workflow to run an Export Currencies            task from Sage 50 and a Display Last Output task.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a36fc6979143615648f7/file-K3FDDTimdD.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a36fc6979143615648f7/file-K3FDDTimdD.png)

Make sure the Input on the Display Last Out task is specified to (Output from previous task).

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb57239033607d708f337d/file-hwWEhh2PKz.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb57239033607d708f337d/file-hwWEhh2PKz.png)

Running this will open the Output File from your Export Currencies task in your default text editor.

## Input Box
In this example, I will use the Input Box task to log a message in the Zynk Info tab using the Log Info Message task.

Firstly, configure your workflow to have an Input Box task and a Log Info Message task. Then, run the            workflow and a Zynk Object dialogue should appear, as shown below.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a3809033603f7da37031/file-b0hO1YVlHs.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a3809033603f7da37031/file-b0hO1YVlHs.png)

As you can see, I am going to echo the words 'hello world!' in my Log Info Message task. The results are shown            below.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a392c6979143615648f8/file-dE1gRtPzCj.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a392c6979143615648f8/file-dE1gRtPzCj.png)

## Log Info Message
In this example, I am troubleshooting a File Repeater task to find out if I am saving my file to the correct location.            In my File Repeater, I'm trying to copy a file from an external directory to my working directory whilst reserving            the file name. So, I want to check I'm looping over the correct external directory and to do this, I know there            are three files in my external directory:

 * copy.txt
 * copy2.txt
 * copy3.txt

I'm going to use my Log Info Message task to write out the name of these three files, and this will confirm I'm looping over            the right directory.

Firstly, I'm going to next my Log Info Message task underneath my File Repeater. You can do this drag and dropping the Log            Info Message Task on to the File Repeater.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb58339033607d708f3389/file-U7f9StJuOk.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb58339033607d708f3389/file-U7f9StJuOk.png)

Then, I am going to configure my Log Info Message settings to write out the current file name using context variables.  More            information can be found on our [File Repeater](file-repeater) article.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb58b99033607d708f3390/file-NDaKazKYYo.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb58b99033607d708f3390/file-NDaKazKYYo.png)

Finally, when I run my workflow the Log Info Message confirms I am looking at the correct directory.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb58ec9033607d708f3391/file-AxeSzXSezI.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb58ec9033607d708f3391/file-AxeSzXSezI.png)

## Message Box
For this example, I will use a Message Box to echo the words 'hello world!'.

Firstly, I am going to add the Message Box task to my workflow. Then, I am going to configure the Input of the task to be            'hello world!'

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a3aa9033603f7da37032/file-nwhzBb7btd.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a3aa9033603f7da37032/file-nwhzBb7btd.png)

Finally, when I run my workflow the following Message Box is displayed.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a3b69033603f7da37033/file-y7LN657IiP.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b0a3b69033603f7da37033/file-y7LN657IiP.png)
