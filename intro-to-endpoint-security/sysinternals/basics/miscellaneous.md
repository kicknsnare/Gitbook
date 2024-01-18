# Miscellaneous



## Bginfo

It automatically displays relevant information about a Windows computer on the desktop's background

```powershell
bginfo -accept eula
```

## RegJump

"This little command-line applet takes a registry path and makes Regedit open to that path. It accepts root keys in standard (e.g. HKEY\_LOCAL\_MACHINE) and abbreviated form (e.g. HKLM)." (official definition)



There are multiple ways to query the Windows Registry without using the Registry Editor, such as via the command line (<mark style="color:blue;">**`reg query`**</mark>) and PowerShell <mark style="color:blue;">**`(Get-Item/Get-ItemProperty`**</mark>).

## Strings

"Strings just scans the file you pass it for UNICODE (or ASCII) strings of a default length of 3 or more UNICODE (or ASCII) characters.
