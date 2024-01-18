# Processes

{% embed url="https://app.gitbook.com/o/aeFeXGlefIRFJAt4D2zG/s/YEchRCx098G4mQw5r5r0/core-windows-processes/processes" %}

## <mark style="color:blue;">System</mark>

Normal Behavior

```bash
Session 0 (csrss.exe & wininit.exe)
Session 1 (csrss.exe & winlogon.exe)

Image Path:  N/A
Parent Process:  None
Number of Instances:  One
User Account:  Local System
Start Time:  At boot time

####### Process Hacker #######
Image Path: C:\Windows\system32\ntoskrnl.exe (NT OS Kernel)
Parent Process: System Idle Process (0)
```

Unusual Behavior

```bash
A parent process (aside from System Idle Process (0))
Multiple instances of System. (Should only be one instance) 
A different PID. (Remember that the PID will always be PID 4)
Not running in Session 0
```

## <mark style="color:blue;">System->smss.exe</mark>

Normal Behavior&#x20;

```
Image Path:  %SystemRoot%\System32\smss.exe
Parent Process:  System
Number of Instances:  One master instance and child instance per session. The child instance exits after creating the session.
User Account:  Local System
Start Time:  Within seconds of boot time for the master instance
```

Unusual Behavior

```bash
A different parent process other than System (4)
The image path is different from C:\Windows\System32
More than one running process. (children self-terminate and exit after each new session)
The running User is not the SYSTEM user
Unexpected registry entries for Subsystem
```

## <mark style="color:blue;">csrss.exe</mark>

If this process is terminated by chance, it will result in system failure.

Normal Behavior&#x20;

```bash
Session 0 (PID 392)
Session 1 (PID 512)
Image Path:  %SystemRoot%\System32\csrss.exe
Parent Process:  Created by an instance of smss.exe
Number of Instances:  Two or more
User Account:  Local System
Start Time:  Within seconds of boot time for the first two instances (for Session 0 and 1). Start times for additional instances occur as new sessions are created, although only Sessions 0 and 1 are often created.
```

Unusual Behavior

```bash
An actual parent process. (smss.exe calls this process and self-terminates)
Image file path other than C:\Windows\System32
Subtle misspellings to hide rogue processes masquerading as csrss.exe in plain sight
The user is not the SYSTEM user.
```

## <mark style="color:blue;">wininit.exe</mark>

Normal Behavior

```bash
Image Path:  %SystemRoot%\System32\wininit.exe
Parent Process:  Created by an instance of smss.exe
Number of Instances:  One
User Account:  Local System
Start Time:  Within seconds of boot time
```

Unusual Behavior

```bash
An actual parent process. (smss.exe calls this process and self-terminates)
Image file path other than C:\Windows\System32
Subtle misspellings to hide rogue processes in plain sight
Multiple running instances
Not running as SYSTEM
```



## <mark style="color:blue;">Wininit -> services.exe</mark>

Normal Behavior

```bash
Image Path:  %SystemRoot%\System32\services.exe
Parent Process:  wininit.exe
Number of Instances:  One
User Account:  Local System
Start Time:  Within seconds of boot time
```

Unusual Behavior

```bash
A parent process other than wininit.exe
Image file path other than C:\Windows\System32
Subtle misspellings to hide rogue processes in plain sight
Multiple running instances
Not running as SYSTEM
```



## <mark style="color:blue;">wininit.exe -> services.exe -></mark> <mark style="color:yellow;">`svchost.exe`</mark>

In the binary path there is a key identifier which is **`-k` This is how a legitimate svchost.exe process is called**

<mark style="color:blue;">**`Since svchost.exe will always have multiple running processes on any Windows system, this process has been a target for malicious use. Adversaries create malware to masquerade as this process and try to hide amongst the legitimate svchost.exe processes. They can name the malware svchost.exe or misspell it slightly, such as scvhost.exe. By doing so, the intention is to go under the radar. Another tactic is to install/call a malicious service (DLL).`**</mark>&#x20;

Normal Behavior

```bash
Image Path: %SystemRoot%\System32\svchost.exe
Parent Process: services.exe
Number of Instances: Many
User Account: Varies (SYSTEM, Network Service, Local Service) depending on the svchost.exe instance. In Windows 10, some instances run as the logged-in user.
Start Time: Typically within seconds of boot time. Other instances of svchost.exe can be started after boot.
```

Unusual Behavior

```bash
A parent process other than services.exe
Image file path other than C:\Windows\System32
Subtle misspellings to hide rogue processes in plain sight
The absence of the -k parameter
```

## <mark style="color:yellow;">`lsass.exe`</mark>

Lsass.exe is another process adversaries target. Common tools such as mimikatz are used to dump credentials, or adversaries mimic this process to hide in plain sight. Again, they do this by either naming their malware by this process name or simply misspelling the malware slightly.

Normal Behavior&#x20;

```bash
Image Path:  %SystemRoot%\System32\lsass.exe
Parent Process:  wininit.exe
Number of Instances:  One
User Account:  Local System
Start Time:  Within seconds of boot time
```

Unusual Behavior

```
A parent process other than wininit.exe
Image file path other than C:\Windows\System32
Subtle misspellings to hide rogue processes in plain sight
Multiple running instances
Not running as SYSTEM
```



## <mark style="color:blue;">winlogon.exe</mark>

Normal Behavior

```bash
Session 1
Image Path:  %SystemRoot%\System32\winlogon.exe
Parent Process:  Created by an instance of smss.exe that exits, so analysis tools usually do not provide the parent process name.
Number of Instances:  One or more
User Account:  Local System
Start Time:  Within seconds of boot time for the first instance (for Session 1). Additional instances occur as new sessions are created, typically through Remote Desktop or Fast User Switching logons.
```

Unusual Behavior

```bash
An actual parent process. (smss.exe calls this process and self-terminates)
Image file path other than C:\Windows\System32
Subtle misspellings to hide rogue processes in plain sight
Not running as SYSTEM
Shell value in the registry other than explorer.exe
```



## <mark style="color:blue;">explorer.exe</mark>

Normal Behavior

```bash
Image Path:  %SystemRoot%\explorer.exe
Parent Process:  Created by userinit.exe and exits
Number of Instances:  One or more per interactively logged-in user
User Account:  Logged-in user(s)
Start Time:  First instance when the first interactive user logon session begins
```

Unusual Behavior

```bash
An actual parent process. (userinit.exe calls this process and exits)
Image file path other than C:\Windows
Running as an unknown user
Subtle misspellings to hide rogue processes in plain sight
Outbound TCP/IP connections
```
