# System

## The PID For System is Always 4

<mark style="color:yellow;">**`It was mentioned in a previous section that a PID for any given process is assigned at random, but that is not the case for the System process.`**</mark>



Process Explorer\
![System properties.](https://assets.tryhackme.com/additional/windows-processes/system.png)\
\
Image Path:  N/AParent Process:  NoneNumber of Instances:  OneUser Account:  Local SystemStart Time:  At boot time\
The information is slightly different if we view the System properties using&#x20;

Process Hacker. \
![System properties (2).](https://assets.tryhackme.com/additional/windows-processes/system2.png)\
\
Image Path: C:\Windows\system32\ntoskrnl.exe (NT OS Kernel)Parent Process: System Idle Process (0)



What is unusual behaviour for this process?

* A parent process (aside from System Idle Process (0))
* Multiple instances of System. (Should only be one instance)&#x20;
* A different PID. (Remember that the PID will always be PID 4)
* Not running in Session 0
