# explorer.exe

The last process we'll look at is Windows Explorer, explorer.exe. This process gives the user access to their folders and files. It also provides functionality for other features, such as the Start Menu and Taskbar.\
As mentioned previously, the Winlogon process runs userinit.exe, which launches the value in `HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon\Shell`. Userinit.exe exits after spawning explorer.exe. Because of this, the parent process is non-existent. \
There will be many child processes for explorer.exe.

\
\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/explorer-tree.png" alt=""><figcaption></figcaption></figure>

\
What is normal?

\


<figure><img src="https://assets.tryhackme.com/additional/windows-processes/explorer.png" alt=""><figcaption></figcaption></figure>

\
\
Image Path:  %SystemRoot%\explorer.exeParent Process:  Created by userinit.exe and exitsNumber of Instances:  One or more per interactively logged-in userUser Account:  Logged-in user(s)Start Time:  First instance when the first interactive user logon session begins\
What is unusual?

* An actual parent process. (userinit.exe calls this process and exits)
* Image file path other than C:\Windows
* Running as an unknown user
* Subtle misspellings to hide rogue processes in plain sight
* Outbound TCP/IP connections



<figure><img src="https://assets.tryhackme.com/additional/windows-processes/explorer-tcpip.png" alt=""><figcaption></figcaption></figure>

\
\
Note: The above image is the explorer.exe properties view from Process Explorer.
