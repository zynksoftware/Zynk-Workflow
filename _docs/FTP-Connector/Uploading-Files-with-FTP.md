---
slug: uploading-files-with-ftp
redirect_from: "/article/252-uploading-files-with-ftp"
title: Uploading Files with FTP
---

This task will upload a file from the local file system to a remote FTP Server.

## Settings
### FTP Connection
_Required_  
The FTP Connection to delete from. See the [Connecting to an FTP Server](connecting-to-an-ftp-server) article here if you require more information on how to create/manage connections.  

### Directory
_Required_  
Initial Directory to move to on FTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of 'Folder, HTTP or FTP location' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.  

### Input File
_Required_  
The file to be uploaded from local PC.

### Output File
_Required_  
The name to save the file on FTP server.  It is important that you use the 'Text or script' data type instead of 'File' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.  

### Overwrite File
_Required_  
Set to true to always overwrite file on server, otherwise file will not be copied to server.

### Retry Count
_Required_  
The number of times to retry the upload if an error occurs.

### Temporary Upload Settings
Settings to allow using a temporary file name during the upload, and then rename once the upload is complete.  See [Temporary Upload Settings](temporary-upload-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [FTP to Sage 50 Integration](ftp-to-sage-50-integration) article.