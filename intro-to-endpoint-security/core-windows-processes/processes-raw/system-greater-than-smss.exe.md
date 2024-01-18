# System > smss.exe

Is responsible for creating new sessions. It is the first user-mode process started by the kernel.\
This process starts the kernel and user modes of the Windows subsystem This subsystem includes win32k.sys (kernel mode), winsrv.dll (user mode), and csrss.exe (user mode).&#x20;

Session 0 (csrss.exe & wininit.exe)\


![Smss.exe session 0.](https://assets.tryhackme.com/additional/windows-processes/smss-session0-tree.png)

\
![csrss.exe properties on session 0.](https://assets.tryhackme.com/additional/windows-processes/smss-session0b.png)\
\
Session 1 (csrss.exe & winlogon.exe)\


![Smss.exe session 1.](https://assets.tryhackme.com/additional/windows-processes/smss-session1-tree.png)

\


![csrss.exe properties on session 1.](https://assets.tryhackme.com/additional/windows-processes/smss-session1b.png)

Any other subsystem listed in the `Required` value of `HKLM\System\CurrentControlSet\Control\Session Manager\Subsystems` is also launched.\
\
\
SMSS is also responsible for creating environment variables, virtual memory paging files and starts winlogon.exe (the Windows Logon Manager).\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/smss-registry.png" alt=""><figcaption></figcaption></figure>

## What is normal?

<figure><img src="https://assets.tryhackme.com/additional/windows-processes/smss.png" alt=""><figcaption></figcaption></figure>

Image Path:  %SystemRoot%\System32\smss.exe

Parent Process:  System

Number of Instances:  One master instance and child instance per session. The child instance exits after creating the session.

User Account:  Local System

Start Time:  Within seconds of boot time for the master instance



## What is unusual?

* A different parent process other than System (4)
* The image path is different from C:\Windows\System32
* More than one running process. (children self-terminate and exit after each new session)
* The running User is not the SYSTEM user
* Unexpected registry entries for Subsystem
