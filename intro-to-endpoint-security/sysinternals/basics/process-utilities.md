# Process Utilities



## Autoruns

Note: This is a good tool to search for any malicious entries created in the local machine to establish Persistence.

```powershell
autoruns
```



## ProcDump

"ProcDump is a command-line utility whose primary purpose is monitoring an application for CPU spikes and generating crash dumps during a spike that an administrator or developer can use to determine the cause of the spike." (official definition)

{% embed url="https://learn.microsoft.com/en-us/sysinternals/downloads/procdump" %}

Alternatively, you can use Process Explorer to do the same.



## Process Explorer

It would be wise to check if the IP is what we assume it is

There is an option within ProcExp to **`Verify`` `**<mark style="color:blue;">**`Signatures`**</mark>**`.`** Once enabled, it shows up as a column within the Process view.

![Screenshot showing the color coding used in the Process Explorer tool](https://assets.tryhackme.com/additional/sysinternals/procexp-colors.png)

```powershell
procexp
```



## Process Monitor

{% embed url="https://adamtheautomator.com/procmon/" %}

To use ProcMon effectively you must use the Filter and must configure it properly.

![](https://assets.tryhackme.com/additional/sysinternals/procmon4.png)

```powershell
procmon
```



## <mark style="color:yellow;">`PsExec`</mark>

PsExec is another tool that is utilized by adversaries. This tool is associated with MITRE techniques [T1570](https://attack.mitre.org/techniques/T1570) (Lateral Tool Transfer), [T1021.002](https://attack.mitre.org/techniques/T1021/002) (Remote Services: SMB/Windows Admin Shares), and [T1569.002](https://attack.mitre.org/techniques/T1569/002) (System Services: Service Execution). It's MITRE ID is [S0029](https://attack.mitre.org/software/S0029/).

{% embed url="https://learn.microsoft.com/en-us/sysinternals/downloads/psexec" %}
