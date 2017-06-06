---
slug: common-wordpress-settings
title: Common WordPress Settings
---

See below the common settings for WordPress export tasks.

## Settings

### Export All
_Required_
Set to true to export all pages, or false to only export those published since the date specified in the 'Export From' setting.

### Export Detailed
_Required_
Set to true to export the related author and parent for each page. When set to false, only the ID of the author and parent will be downloaded. Please note that setting this to true will significantly increase the amount of time the export takes.

### Export From
_Required_
When the 'Export All' setting is false, only pages published after this date will be exported. This date will update automatically each time  the task runs.

### Page Size
_Required_
The number of records to include in each page of results. Defaults to 10. Increasing this value will increase the speed of the export, but will consume more memory.

### Search
_Required_
Enter search keywords to filter the results returned.