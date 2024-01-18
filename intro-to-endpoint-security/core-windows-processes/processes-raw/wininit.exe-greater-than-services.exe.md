# wininit.exe > services.exe

he next process is the Service Control Manager (SCM) or services.exe. Its primary responsibility is to handle system services: loading services, interacting with services and starting or ending services. It maintains a database that can be queried using a Windows built-in utility, `sc.exe`.&#x20;

```shell-session
C:\Users\Administrator> sc.exe
DESCRIPTION:
        SC is a command line program used for communicating with the
        Service Control Manager and services.
USAGE:
        sc <server> [command] [service name] <option1> <option2>...
```

\
Information regarding services is stored in the registry, `HKLM\System\CurrentControlSet\Services`. \
![Service Registry.](https://assets.tryhackme.com/additional/windows-processes/services-registry.png)\
\
This process also loads device drivers marked as auto-start into memory. \
When a user logs into a machine successfully, this process is responsible for setting the value of the Last Known Good control set (Last Known Good Configuration), `HKLM\System\Select\LastKnownGood`, to that of the CurrentControlSet. \
![LastKnownGood Registry Key.](https://assets.tryhackme.com/additional/windows-processes/lastknowngood.png)\
\
This process is the parent to several other key processes: svchost.exe, spoolsv.exe, msmpeng.exe, and dllhost.exe, to name a few. You can read more about this process [here](https://en.wikipedia.org/wiki/Service\_Control\_Manager).\
![Services.exe process tree.](https://assets.tryhackme.com/additional/windows-processes/services-tree.png)\
\
What is normal?\
![Services.exe properties.](https://assets.tryhackme.com/additional/windows-processes/services.png)\
\
![Services.exe properties (2).](https://assets.tryhackme.com/additional/windows-processes/services2.png)\
\
Image Path:  %SystemRoot%\System32\services.exeParent Process:  wininit.exeNumber of Instances:  OneUser Account:  Local SystemStart Time:  Within seconds of boot time\
What is unusual?

* A parent process other than wininit.exe
* Image file path other than C:\Windows\System32
* Subtle misspellings to hide rogue processes in plain sight
* Multiple running instances
* Not running as SYSTEM
