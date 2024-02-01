# Walkthrough

\
Sysmon also collects the Hash value of the processes being created. What is the MD5 HASH of the program 3791.exe?&#x20;

```bash
index="botsv1" "3791.exe" sourcetype=xmlwineventlog EventCode=1 hashes
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/791e3844449959e9652dda238a82d9fc94843134a5f39b762e04955bbfe74373/68747470733a2f2f692e696d6775722e636f6d2f6e4d5a4d4847412e706e67" alt=""><figcaption></figcaption></figure>

Looking at the logs, which user executed the program 3791.exe on the server?

&#x20;

<figure><img src="https://camo.githubusercontent.com/4d1c17a200f3b5c902f187eb7696daa0999f58dd39ac70fdb5047daf394d7523/68747470733a2f2f692e696d6775722e636f6d2f63516c68696b312e706e67" alt=""><figcaption></figcaption></figure>



Search hash on the virustotal. What other name is associated with this file 3791.exe?

\


<figure><img src="https://camo.githubusercontent.com/be6eccd2813359a52efe8d384b501eeff834cb5170a229f866a8a9949945c16d/68747470733a2f2f692e696d6775722e636f6d2f6d53486f654c582e706e67" alt=""><figcaption></figcaption></figure>
