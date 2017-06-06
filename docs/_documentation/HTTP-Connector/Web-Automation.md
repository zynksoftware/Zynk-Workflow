---
slug: web-automation
redirect_from: "/article/723-web-automation"
title: Web Automation
---
This task will perform a series of actions on the web. For example, this may involve browsing to a particular web page, entering some text and then clicking a button. The task works using Selenium WebDriver and PhantomJS.

**Note:** This task is not included in the standard installation of Zynk. If you can't see this task in the task library, you can install from Extensions -> Extensions Manager -> Additions Tab.  You will need to restart Zynk in order for the tasks to show in the task library.

## Settings
### Action List
_Required_  
The list of actions to perform on the web. The actions will be performed in sequential order. See below for more details on configuring the list of actions.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Configuring the Action List
The action list is configured by clicking the ellipsis (...) button next to the Action List setting. You will see a screen like the one below.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56cb178bc697915005a7369f/file-Ff16rBH1XH.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56cb178bc697915005a7369f/file-Ff16rBH1XH.png)

1. Click the 'Add' button to add a new action to the list.
2. Choose the type of action to perform from the drop down. The available actions are documented below.
3. The action's settings will appear here. Configure them according to the instructions for the action shown below.
4. Any unwanted actions can be removed by clicking the red cross. Actions can be re-ordered by clicking and dragging.
5. Click OK once all of the actions have been added and configured.

## Actions
There are several different actions supported by the task. Each one is outlined below, along with a description of each of it's settings.

#### Browse To
This action will browse to a specified web page. It only has one setting:

 *  **Uri** - Enter the URL of the web page to browse to (e.g. [www.google.co.uk](http://www.google.co.uk)).

#### Click
This action will click a button on the current web page. It has the following settings:

 * **Lookup Element By** - Select a method for searching for the button to click.
 * **Element Lookup Value** - Enter the value to search for.

#### Custom Action
This action will execute a custom razor script. It has the following settings:

 * **Razor Template** - Enter the custom razor code to run. The underlying PhantonJSDriver instance used by the task can be accessed in the razor script using `Context.Object`.
 * **Referenced Assemblies** - If you need to reference any additional DLLs, enter the file paths here.
 * **Namespaces** - Enter any namespaces to use here.

#### Download File
This action will download a file from a specified URL. It has the following settings:

 * **Uri** - Enter the URL of the file to download.
 * **Output File** - Enter the file to save the downloaded file to.

#### Execute Javascript
This action will execute Javascript on the current web page. It has the following settings:

 * **Script** - Enter the URL of the file to download.
 * **Output Variable Name** - Optionally enter a variable name to save the output from the script to. The value can be accessed in subsequent actions, by enabling the 'Use Razor Engine' option, and using `@(Context.Current["YourVariableName"])`.

#### Save Page
This action will save the current web page to a HTML file. It only has one setting:

 * **Output File** - Enter the file to save the web page to.

#### Set Field Value
This action will set the value of a text box, drop down or check box on the current web page. It has the following settings:

 * **Value** - Enter the new value for the field. When setting the value of a check box, the value should be either 'true' or 'false'.
 * **Lookup Element By** - Select a method for searching for the field.
 * **Element Lookup Value** - Enter the value to search for.

#### Wait For Element
This action will wait for an element to appear on the current web page. It can be useful when dealing with web pages where the content is loaded dynamically, and can be used to make the task wait until certain content has loaded. It has the following settings:

 * **Timeout (seconds)** - Enter the maximum time (in seconds) to wait for the specified element to appear on the page.
 * **Lookup Element By** - Select a method for searching for the element.
 * **Element Lookup Value** - Enter the value to search for.

#### Wait For Javascript
This action will wait until any scripts on the page have finished executing. t can be useful when dealing with web pages where the content is  loaded dynamically, and can be used to make the task wait until certain  content has loaded. It has the following settings:

 * **Timeout (seconds)** - Enter the maximum time (in seconds) to wait for the specified element to appear on the page.

## Examples
Performing a Google search for 'Zynk':

1. Add a 'Browse To' action to the list, and set the URL [http://www.google.co.uk](http://www.google.com/)
2. Add a 'Set Field Value' action to the list, set 'Lookup Element By' to Id, set 'Element Lookup Value' to 'lst-ib', and set 'Value' to 'Zynk'.
3. Add a 'Click' action to the list, set 'Lookup Element By' to Name and set 'Element Lookup Value' to 'btnK'.
4. Add a 'Save Page' action to the list, and set 'Output File' to 'search\_results.html'.

TIP: To find the correct Element Lookup Value to use for an element, open the web page in Firefox or Chrome, right click the element, and click 'Inspect Element'.