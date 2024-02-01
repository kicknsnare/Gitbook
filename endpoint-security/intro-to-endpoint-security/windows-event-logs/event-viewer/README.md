# Event Viewer

The Windows Event Logs are not text files that can be viewed using a text editor. However, the raw data can be translated into XML using the Windows API. The events in these log files are stored in a proprietary binary format with a .evt or .evtx extension. The log files with the .evtx file extension typically reside in `C:\Windows\System32\winevt\Logs`.\


* <mark style="color:blue;">**`System Logs:`**</mark> Records events associated with the Operating System segments.
* <mark style="color:blue;">**`Security Logs:`**</mark> Records events connected to logon and logoff activities on a device.&#x20;
* <mark style="color:blue;">**`Application Logs`**</mark>: Records events related to applications installed on a system.
* <mark style="color:blue;">**`Directory Service Events`**</mark>: Active Directory changes and activities are recorded in these logs
* <mark style="color:blue;">**`File Replication Service Events:`**</mark> Records events associated with Windows Servers during the sharing of Group Policies and logon scripts to domain controllers, from where they may be accessed by the users through the client servers.
* <mark style="color:blue;">`DNS Event Logs:`</mark> DNS servers use these logs to record domain events and to map out
* <mark style="color:blue;">**`Custom Logs:`**</mark> Events are logged by applications that require custom data storage.&#x20;

There are 5 types of events that can be logged

<figure><img src="https://assets.tryhackme.com/additional/win-event-logs/five-event-types.png" alt=""><figcaption></figcaption></figure>

Event Viewer has three panes.

1. The pane on the left provides a hierarchical tree listing of the event log providers.
2. The pane in the middle will display a general overview and summary of the events specific to a selected provider.
3. The pane on the right is the actions pane.

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/e2ceaa065e80a6763b7a861dbd4142fb.gif" alt=""><figcaption></figcaption></figure>



## Applications and Services Logs&#x20;

Expand this section and drill down on `Microsoft > Windows > PowerShell > Operational.`

Notice the <mark style="color:blue;">**`Clear Log button`**</mark> at the bottom right. There are legitimate reasons to use this button, such as during security maintenance, but adversaries will likely attempt to clear the logs to go undetected. Note: This is not the only method to remove the event logs for any given event provider.

\


<figure><img src="https://assets.tryhackme.com/additional/win-event-logs/posh-operational-1b.png" alt=""><figcaption></figcaption></figure>

* Level: Highlights the log recorded type based on the identified event types specified earlier. In this case, the log is labeled as Information.
* Date and Time: Highlights the time at which the event was logged.
* Source: The name of the software that logs the event is identified. From the above image, the source is PowerShell.
* Event ID: This is a predefined numerical value that maps to a specific operation or event based on the log source. This makes Event IDs not unique, so `Event ID 4103` in the above image is related to Executing Pipeline but will have an entirely different meaning in another event log.
* Task Category: Highlights the Event Category. This entry will help you organize events so the Event Viewer can filter them. The event source defines this column.

The Create Custom View and Filter Current Log are nearly identical. The only difference between the 2 is that the `By log` and `By source` radio buttons are greyed out in Filter Current Log. What is the reason for that? The filter you can make with this specific action only relates to the current log. Hence no reason for 'by log' or 'by source' to be enabled.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/a06823a8acefe78317235bf66d02152d.gif" alt=""><figcaption></figcaption></figure>

\
\
Why are these actions beneficial? Say, for instance, you don't want all the events associated with PowerShell/Operational cluttering all the real estate in the pane. Maybe you're only interested in 4104 events. That is possible with these two actions. \
To view event logs from another computer, right-click `Event Viewer (Local) > Connect to Another Computer...`\


![Menu option on how to connect to another computer to view its logs.](https://assets.tryhackme.com/additional/win-event-logs/remote-computer.png)
