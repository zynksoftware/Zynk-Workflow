---
slug: temporary-upload-settings
redirect_from: "/article/253-temporary-upload-settings"
title: Temporary Upload Settings
---
The following settings are available on the FTP Upload task, to allow a temporary file name to be used during the upload. The file will be renamed once the upload is complete. This setting can be useful when the files uploaded to the FTP server are processed automatically, as it can be used to prevent the files being processed before the upload has completed.

## Settings
### Setting
_Required_  
 * TemporaryFile - to use give the output file a different file extension whilst the upload is taking place.
 * TemporaryDirectory - to place the output file in a sub-directory whilst the upload is taking place.
 * NotEnabled - to disable the use of a temporary file extension or directory.

### Temporary Directory
_Optional_  
The sub-directory to save the file to whilst the upload is taking place

### Temporary File Extension
_Optional_  
The file extension to use whilst the upload is taking place (eg .tmp).