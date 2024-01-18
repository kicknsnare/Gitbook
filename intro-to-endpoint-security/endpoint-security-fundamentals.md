# 🔍 Endpoint Security Fundamentals

## Core Windows Processes

Note: ">" symbol represents a parent-child relationship. `System (Parent) > smss.exe (Child)`

* System
* System > smss.exe
* csrss.exe
* wininit.exe
* wininit.exe > services.exe
* wininit.exe > services.exe > svchost.exe
* lsass.exe
* winlogon.exe
* explorer.exe

In addition, <mark style="color:yellow;">the processes with no depiction of a parent-child relationship should not have a Parent Process under normal circumstances</mark>, except for the System process, which should only have <mark style="color:yellow;">**`System Idle Process (0)`**</mark> as its parent process.

## Sysinternals

Analyzing artefacts in the backend of a Windows Machine.

## TCPView

Networking Utility tool. Detailed listings of all TCP and UDP endpoints on your system



## Process Explorer

Shows a list of the currently active processes, including the names of their owning accounts
