# Simple Guide

<mark style="color:blue;">**`live.sysinternals.com/`**</mark> or <mark style="color:blue;">**`\\live.sysinternals.com\tools<toolname>`**</mark>



<mark style="color:blue;">**`\\live.sysinternals.com\tools\<toolname>`**</mark>

If it fails&#x20;

```powershell
get-service webclient
start-service webclient
control.exe /name Microsoft.NetworkAndSharingCenter
-> Change advanced sharing settings 
-> Turn on network discovery
#WebDAV Redirector not installed
Install-WindowsFeature WebDAV-Redirector –Restart
#Check
Get-WindowsFeature WebDAV-Redirector | Format-Table –Autosize
```

