---
slug: using-file-library
redirect_from: "/article/631-using-file-library"
title: Using File Library
---
This article will show you how to use some of the tasks available in the file library using a sample workflow. The file library is free when you purchase Zynk, so can be utilised at no extra cost.

## Copy File
Firstly, I have created a simple text file (copy.txt) that I am going to copy from the `C:\ProgramData\Internetware\Zynk\1.0\Data` folder to my working directory.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb4fd4c697917fdc55db0e/file-yXnlH71XrE.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb4fd4c697917fdc55db0e/file-yXnlH71XrE.png)

I have set up my Zynk workflow to copy this file to my working directory, see below.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09c79c6979143615648d8/file-TEnJY3115x.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09c79c6979143615648d8/file-TEnJY3115x.png)

And after running the workflow, below you can see my file has been copied successfully to my working directory.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb51599033607d708f334e/file-aqUi5W8uMb.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb51599033607d708f334e/file-aqUi5W8uMb.png)

## Delete File
I have created a simple text file that I am going to delete using Zynk, see below.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb52fe9033607d708f335f/file-Mb9QeppJWJ.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb52fe9033607d708f335f/file-Mb9QeppJWJ.png)

See the below configuration of my workflow to delete the above file.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09c9a9033603f7da3700c/file-qRTbPnIOvG.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09c9a9033603f7da3700c/file-qRTbPnIOvG.png)

## File Repeater
The file repeater tasks is used to repeat a process for any files within a specified directory. For example, as the below example suggests, I am planning to copy any files with an extension of .txt to another directory.

In order to reference each file successfully, you'll need to use context variables. If you haven't used these before, please see [File Repeater](file-repeater) on how to use them.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb526f9033607d708f3357/file-WmgroW9Unq.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb526f9033607d708f3357/file-WmgroW9Unq.png)

I am going to copy the above files in to my working directory with Zynk using the below configuration.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09ca7c6979143615648d9/file-XbwPl0dgV1.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09ca7c6979143615648d9/file-XbwPl0dgV1.png)

You can find a sample workflow for all File Library tasks on our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples)