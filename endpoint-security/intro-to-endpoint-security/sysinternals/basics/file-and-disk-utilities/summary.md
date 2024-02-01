# Summary



## Sigcheck

Utility that shows file version number, timestamp information, and digital signature details, including certificate chains.

{% embed url="https://learn.microsoft.com/en-us/sysinternals/downloads/sigcheck" %}

```powershell
sigcheck [-a][-h][-i][-e][-l][-n][[-s]|[-c|-ct]|[-m]][-q][-r][-u][-vt][-v[r][s]][-f catalog file] <file or directory>

sigcheck -d [-c|-ct] <file or directory>

usage: sigcheck -t[u][v] [-i] [-c|-ct] <certificate store name|*>
```

**`sigcheck -u -e C:\Windows\System32`**

## Streams



```powershell
streams <filepath> accepteula
streams [-s] [-d] <file or directory>
```



## <mark style="color:yellow;">`Sdelete`</mark>

It allows you to delete one or more files and/or directories, or to cleanse the free space on a logical disk

SDelete has been used by adversaries and is associated with MITRE techniques [T1485](https://attack.mitre.org/techniques/T1485/) (Data Destruction) and [T1070.004](https://attack.mitre.org/techniques/T1070/004/) (Indicator Removal on Host: File Deletion). It's MITRE ID [S0195](https://attack.mitre.org/software/S0195/).
