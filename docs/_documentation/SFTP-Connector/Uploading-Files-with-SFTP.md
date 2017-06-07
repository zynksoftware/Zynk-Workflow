---
slug: uploading-files-with-sftp
redirect_from: "/article/306-uploading-files-with-sftp"
title: Uploading Files with SFTP
---
This task will upload one or more files from the local file system to a remote SFTP Server.

## Settings
### Connection
_Required_  
The SFTP Connection to delete from.  See the [Connecting to an SFTP Server](connecting-to-an-sftp-server) if you require more information on how to create/manage connections.

### Directory
_Required_  
The directory to move to on SFTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of 'Folder, HTTP or FTP location' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.

### Input File
_Required_  
The file to be uploaded from local PC. To upload multiple files, you can use the 'Use a list' option in the Zynk Object editor, or the output from a [List Files](list-files) task.

### Output File
_Required_  

The name to save the file on SFTP server.  It is important that you use the 'Text or script' data type instead of 'File' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system. 

### Overwrite File
_Required_  
Set to true to allow the file to be overwritten on server if it already exists.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [SFTP to Sage 50 Integration](sftp-to-sage-50-integration) article.