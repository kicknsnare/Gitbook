# Hunting Metasploit

## Check&#x20;

Port 4444

Port 5555

```powershell
Event ID 3
*/EventData/Data[@Name="DestinationPort"]
*/EventData/Data=4444
```

```powershell
Get-WinEvent -Path <Path to Log> -FilterXPath '*/System/EventID=3 and */EventData/Data[@Name="DestinationPort"] and */EventData/Data=4444'
```
