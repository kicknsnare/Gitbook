# wininit.exe > services.exe > svchost.exe

The Service Host (Host Process for Windows Services), or svchost.exe, is responsible for hosting and managing Windows services.&#x20;

\
\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/dcomlaunch.png" alt=""><figcaption></figcaption></figure>

\
The services running in this process are implemented as DLLs. The DLL to implement is stored in the registry for the service under the `Parameters` subkey in `ServiceDLL`. The full path is `HKLM\SYSTEM\CurrentControlSet\Services\SERVICE NAME\Parameters`.\
The example below is the ServiceDLL value for the Dcomlaunch service.

\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/servicedll.png" alt=""><figcaption></figcaption></figure>

\
\
To view this information from within Process Hacker, right-click the svchost.exe process. In this case, it will be PID 748.

\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/dcomlaunch2.png" alt=""><figcaption></figcaption></figure>

\
\
Right-click the service and select Properties. Look at Service DLL.

\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/dcomlaunch3.png" alt=""><figcaption></figcaption></figure>

\
\
From the above screenshot, the Binary Path is listed.\
Also, notice how it is structured. There is a key identifier in the binary path, and that identifier is `-k` . This is how a legitimate svchost.exe process is called. \
The -k parameter is for grouping similar services to share the same process. This concept was based on the OS design and implemented to reduce resource consumption. Starting from Windows 10 Version 1703, services grouped into host processes changed. On machines running more than 3.5 GB of memory, each service will run its own process. You can read more about this process [here](https://en.wikipedia.org/wiki/Svchost.exe).\
Back to the key identifier (-k) from the binary path, in the above screen, the -k value is Dcomlaunch. Other services are running with the same binary path in the virtual machine attached to this room.

\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/shared-process.png" alt=""><figcaption></figcaption></figure>

\
\
Each will have a different value for ServiceDLL. Let's take LSM as an example and inspect the value for ServiceDLL.

\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/lcm.png" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/lcm2.png" alt=""><figcaption></figcaption></figure>

\
Since svchost.exe will always have multiple running processes on any Windows system, this process has been a target for malicious use. Adversaries create malware to masquerade as this process and try to hide amongst the legitimate svchost.exe processes. They can name the malware svchost.exe or misspell it slightly, such as scvhost.exe. By doing so, the intention is to go under the radar. Another tactic is to install/call a malicious service (DLL).  \
Extra reading - [Hexacorn Blog](https://www.hexacorn.com/blog/2015/12/18/the-typographical-and-homomorphic-abuse-of-svchost-exe-and-other-popular-file-names/)\
What is normal?\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/svchost.png" alt=""><figcaption></figcaption></figure>

\
Image Path: %SystemRoot%\System32\svchost.exeParent Process: services.exeNumber of Instances: ManyUser Account: Varies (SYSTEM, Network Service, Local Service) depending on the svchost.exe instance. In Windows 10, some instances run as the logged-in user.Start Time: Typically within seconds of boot time. Other instances of svchost.exe can be started after boot.\
What is unusual?

* A parent process other than services.exe
* Image file path other than C:\Windows\System32
* Subtle misspellings to hide rogue processes in plain sight
* The absence of the -k parameter
