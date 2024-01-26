# Get-WinEvent



## Useful Commnand

```powershell
Get-WinEvent -FilterHashtable @{LogName='Microsoft-Windows-PowerShell/Operational'; ID=4104} | Select-Object -Property Message | Select-String -Pattern 'SecureString'
```

{% embed url="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-5.1" %}

* By default, `Get-WinEvent` returns event information in the order of newest to oldest.
* To interrupt the command, press CTRL+C.
* When working with large event logs, per Microsoft, it's inefficient to send objects down the pipeline to a `Where-Object` command. The use of the Get-WinEvent cmdlet's FilterHashtable parameter is recommended to filter event logs.

```powershell
# Get all logs from a computer
Get-WinEvent -ListLog *
# Get event log providers and log names
Get-WinEvent -ListProvider *
#Log filtering
Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'WLMS' }
```



Guidelines for defining a hash table are:

```powershell
@{ <name> = <value>; [<name> = <value> ] ...}
```

* Begin the hash table with an @ sign.
* Enclose the hash table in braces {}
* Enter one or more key-value pairs for the content of the hash table.
* Use an equal sign (=) to separate each key from its value.

```powershell
Get-WinEvent -FilterHashtable @{
  LogName='Application' 
  ProviderName='WLMS' 
}
```

Note: You don't need to use a semicolon if you separate each key/value with a new line, as in the screenshot above for the -FilterHashtable for `ProviderName='WLMS'`.&#x20;



Below is a table that displays the accepted key/value pairs for the Get-WinEvent FilterHashtable parameter.

![Get-WinEvent acceptable key/value pairs for the FilterHashtable parameter](https://assets.tryhackme.com/additional/win-event-logs/filter-hashtable.png)

When building a query with a hash table, Microsoft recommends making the hash table one key-value pair at a time. Event Viewer can provide quick information on what you need to build your hash table.

![Windows Event Viewer displaying information about MsiInstaller application](https://assets.tryhackme.com/additional/win-event-logs/build-hash-table.png)

\
\
![FilterHashtable being applied on the Application logs for MsiInstaller as the ProviderName.](https://assets.tryhackme.com/additional/win-event-logs/msi-installer.png)
