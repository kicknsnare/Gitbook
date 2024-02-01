# Walkthrough

\
How many events were collected and Ingested in the index main?\
&#x20;

<figure><img src="https://camo.githubusercontent.com/b99ff809ce05583fb033e4e02c9160da90a75d2f8a3d33f13c7c7c03aedf5d55/68747470733a2f2f692e696d6775722e636f6d2f586d43495237312e706e67" alt=""><figcaption></figcaption></figure>

On one of the infected hosts, the adversary was successful in creating a backdoor user. What is the new username?\


```splunk-spl
index=main (EventID="4720" OR EventID="4722" OR EventID="4738")
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/fd4c98192e28bc34a00a0353da49b455edb79bafbbf4a85c35f78c68799f052a/68747470733a2f2f692e696d6775722e636f6d2f5047745650714e2e706e67" alt=""><figcaption></figcaption></figure>

On the same host, a registry key was also updated regarding the new backdoor user. What is the full path of that registry key?

```splunk-spl
index=main Category="Registry object added or deleted (rule: RegistryEvent)" A1berto
```

&#x20;We can also see it in Registry Value Set and it is even clearer

<figure><img src="https://camo.githubusercontent.com/86434398c15bf215998d6a455d3cac346ca6170410ca0766f609719f6006edf3/68747470733a2f2f692e696d6775722e636f6d2f4c766f68594a6e2e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/26744f1f5575107a8b0f22ed194f7ffb1c0a21b09a1b82d02c89d190379ffe23/68747470733a2f2f692e696d6775722e636f6d2f506d676d3747532e706e67" alt=""><figcaption></figcaption></figure>

Examine the logs and identify the user that the adversary was trying to impersonate.\
&#x20;If we look for usernames we will find the legitimate users

<figure><img src="https://camo.githubusercontent.com/ada458e7978c6032e816be847a039f0a0975dd3b2d315e122ce4f7adef573901/68747470733a2f2f692e696d6775722e636f6d2f547570513170352e706e67" alt=""><figcaption></figcaption></figure>



What is the command used to add a backdoor user from a remote computer?\
&#x20;

<figure><img src="https://camo.githubusercontent.com/d233b888d70deeb57bf1314a9fdcd2268b0b4cb8877ffa11820bd947c602d0e4/68747470733a2f2f692e696d6775722e636f6d2f447769503833612e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/7cc4059c3ca0019d772f5726253aaecd8414c626d5fdbe43ebf55264103d7731/68747470733a2f2f692e696d6775722e636f6d2f35396669756d4d2e706e67" alt=""><figcaption></figcaption></figure>

How many times was the login attempt from the backdoor user observed during the investigation?\
Login Attempt's Event ID = 4624

```splunk-spl
index=main EventID="4624"
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/bca221f37dc7eedb3758b7434f8ffe47cee4cc8fe6dba6370d146f9d4a05b70b/68747470733a2f2f692e696d6775722e636f6d2f663461693863662e706e67" alt=""><figcaption><p>There is no login attempt from our user</p></figcaption></figure>

What is the name of the infected host on which suspicious Powershell commands were executed?

&#x20;There are only 3 options and the other onces don't have any powershell commands&#x20;

<figure><img src="https://camo.githubusercontent.com/25385eed3256cbb7d622810511a2c43c983b47c63ec0b06f32695930b12e96ef/68747470733a2f2f692e696d6775722e636f6d2f583234455841752e706e67" alt=""><figcaption></figcaption></figure>

PowerShell logging is enabled on this device. How many events were logged for the malicious PowerShell execution?

Powershell Logging Enabled Event ID = 4103

```splunk-spl
index=main EventID="4103"
```

An encoded Powershell script from the infected host initiated a web request. What is the full URL?

```splunk-spl
index=main powershell
```

Looking into the messages field we will find a large message with base64 encoding

&#x20;

<figure><img src="https://camo.githubusercontent.com/b2b43874d89b7477af898c84f24a5fd0d5f0b8b3ff07aa2f66f9cd681618ccde/68747470733a2f2f692e696d6775722e636f6d2f6d61474433446c2e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/afaf6edf3c4cf11356d3a0df5259402aa8c14d3d15cdaa946c6f1c4cc801ba30/68747470733a2f2f692e696d6775722e636f6d2f4d7a5957506e582e706e67" alt=""><figcaption></figcaption></figure>

hxxp\[://]10\[.]10\[.]10\[.]5/news\[.]php
