# Task Manager Raw

\
Weird. Not seeing much, eh? Within a Windows system, many processes are running. Click on `More details`.&#x20;

![Task Manager - More Details.](https://assets.tryhackme.com/additional/windows-processes/taskmanager-3.png)\


Ok, now we're getting somewhere. Notice the five tabs within Task Manager. By default, the current tab is `Processes`.&#x20;

Note: If you're running Task Manager on your Windows machine, you might see additional tabs. \


As shown above, you may notice the processes are categorized as follows: `Apps` and `Background processes`. Another category that is not visible in the above image is `Windows processes`.&#x20;

The columns are very minimal. The columns Name, Status, CPU, and Memory are the only ones visible. To view more columns, right-click on any column header to open more options.&#x20;

![Task Manager actions.](https://assets.tryhackme.com/additional/windows-processes/taskmanager-4.png)\


![Task Manager view.](https://assets.tryhackme.com/additional/windows-processes/taskmanager-5.png)\


The view looks a little better. Let's briefly go over each column (excluding Name, of course):&#x20;

* Type - Each process falls into 1 of 3 categories (Apps, Background process, or Windows process).
* Publisher - Think of this column as the name of the author of the program/file.
* PID - This is known as the process identifier number. Windows assigns a unique process identifier each time a program starts. If the same program has multiple running processes, each will have its unique process identifier (PID).
* Process name - This is the file name of the process. In the above image, the file name for Task Manager is Taskmrg.exe.&#x20;
* Command line - The full command used to launch the process.&#x20;
* CPU - The amount of CPU (processing power) the process uses.
* Memory - The amount of physical working memory utilized by the process.&#x20;

Task Manager is a utility you should be comfortable using, whether you're troubleshooting or performing analysis on the endpoint.&#x20;

Let's move to the `Details` tab. This view provides some core processes that will be discussed in this room. Sort the PID column so that the PIDs are in ascending order.

![Task Manager process details.](https://assets.tryhackme.com/additional/windows-processes/taskmanager-6.png)\


Add some additional columns to see more information about these processes. Good columns to add are `Image path name` and `Command line`.

These two columns can quickly alert an analyst of any outliers with a given process. In the below image, PID 384 is paired with a process named svchost.exe, a Windows process, but if the Image path name or Command line is not what it's expected to be, then we can perform a deeper analysis of this process.&#x20;

![Task Manager process details (2).](https://assets.tryhackme.com/additional/windows-processes/taskmanager-7.png)\


Of course, you can add as many columns as you wish, but adding the columns that would be pertinent to your current task is recommended.&#x20;

Task Manager is a powerful built-in Windows utility but lacks certain important information when analyzing processes, such as parent process information. It is another key column when identifying outliers. Back to svchost.exe, if the parent process for PID 384 is not services.exe, this will warrant further analysis.&#x20;

To further prove this point, where is services.exe?&#x20;

![Task Manager process details (3).](https://assets.tryhackme.com/additional/windows-processes/taskmanager-8.png)\


Based on the above image, the PID for services.exe is 632. But wait, one of the svchost.exe processes has a PID of 384. How did svchost.exe start before services.exe? Well, it didn't. Task Manager doesn't show a Parent-Child process view. That is where other utilities, such as Process Hacker and Process Explorer, come to the rescue.

Process Hacker

![Process hacker.](https://assets.tryhackme.com/additional/windows-processes/processhacker.png)\


Process Explorer

![Process Explorer.](https://assets.tryhackme.com/additional/windows-processes/process-explorer.png)\


Moving forward, we'll use Process Hacker and Process Explorer instead of Task Manager to obtain information about each Windows process. \


As always, it's encouraged that you inspect and familiarize yourself with all information available within Task Manager. It's a built-in utility that is available in every Windows system. You might find yourself in a situation where you can't bring your tools to the fight and rely on the tools native to the system.

Aside from Task Manager, it would be best if you also familiarize yourself with the command-line equivalent of obtaining information about the running processes on a Windows system: `tasklist`, `Get-Process` or `ps` (PowerShell), and `wmic`.
