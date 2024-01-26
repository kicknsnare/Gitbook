# XPath Queries

{% embed url="https://learn.microsoft.com/en-us/previous-versions/dotnet/netframework-4.0/ms256115(v=vs.100)" %}

{% embed url="https://learn.microsoft.com/en-us/windows/win32/wes/consuming-events#xpath-10-limitations" %}

<figure><img src="https://assets.tryhackme.com/additional/win-event-logs/xpath-2.png" alt=""><figcaption></figcaption></figure>

## Simple

<figure><img src="https://assets.tryhackme.com/additional/win-event-logs/xpath-3a.png" alt=""><figcaption></figcaption></figure>

```powershell
Get-WinEvent -LogName Application -FilterXPath '*/System/EventID=100'
```

## Adding more things

<figure><img src="https://assets.tryhackme.com/additional/win-event-logs/xpath-3a.png" alt=""><figcaption></figcaption></figure>

```powershell
Get-WinEvent -LogName Application -FilterXPath '*/System/Provider[@Name="WLMS"]'
#We can combine 2
Get-WinEvent -LogName Application -FilterXPath '*/System/EventID=101 and */System/Provider[@Name="WLMS"]'
```

## Event Data

<figure><img src="https://assets.tryhackme.com/additional/win-event-logs/xpath-7b.png" alt=""><figcaption></figcaption></figure>

```powershell
Get-WinEvent -LogName Security -FilterXPath '*/EventData/Data[@Name="TargetUserName"]="System"'
```



## System Time

```powershell
Get-WinEvent -Logname Application -FilterXPath '*/System/TimeCreated[@SystemTime='
```
