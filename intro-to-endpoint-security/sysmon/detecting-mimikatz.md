# Detecting Mimikatz

<mark style="color:blue;">**`If LSASS is accessed by a process other than`**</mark><mark style="color:blue;">**` `**</mark>_<mark style="color:blue;">**`svchost.exe`**</mark>_<mark style="color:blue;">**` `**</mark><mark style="color:blue;">**`it should be considered suspicious behavior and should be investigated further`**</mark>



```powershell
EventID=10
*/EventData/Data[@Name="TargetImage"]
*/EventData/Data="C:\Windows\system32\lsass.exe"'
```

```powershell
Get-WinEvent -Path <Path to Log> -FilterXPath '*/System/EventID=10 and */EventData/Data[@Name="TargetImage"] and */EventData/Data="C:\Windows\system32\lsass.exe"'
```
