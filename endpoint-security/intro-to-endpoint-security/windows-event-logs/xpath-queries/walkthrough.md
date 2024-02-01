# Walkthrough

\
Using the knowledge gained on Get-WinEvent and XPath, what is the query to find WLMS events with a System Time of 2020-12-15T01:09:08.940277500Z?

```powershell
 Get-WinEvent -Logname Application -FilterXPath '*/System/Provider[@Name="WLMS"] and */System/TimeCreated[@SystemTime=2020-12-15T01:09:08.940277500Z]'
```

Using Get-WinEvent and XPath, what is the query to find a user named Sam with an Logon Event ID of 4720?

```powershell
Get-WinEvent -Logname Security -FilterXPath '*/EventData/Data[@Name="TargetUsername"]="Sam" and */System/EventId=4720'
```

Based on the previous query, how many results are returned?

&#x20;

<figure><img src="https://camo.githubusercontent.com/137a0fd691e26b3686ed0fb03795dd725292a1f50feb5cb2cd012052e1127796/68747470733a2f2f692e696d6775722e636f6d2f77534638584a4e2e706e67" alt=""><figcaption></figcaption></figure>

Based on the output from the question #2, what is Message?





Still working with Sam as the user, what time was Event ID 4724 recorded? (MM/DD/YYYY H:MM:SS \[AM/PM])

&#x20;

<figure><img src="https://camo.githubusercontent.com/94273535b26a8cb218b638c9f7e4f2a29709a408915e2396a07986f2d51cc674/68747470733a2f2f692e696d6775722e636f6d2f484556304139612e706e67" alt=""><figcaption></figcaption></figure>

What is the Provider Name?
