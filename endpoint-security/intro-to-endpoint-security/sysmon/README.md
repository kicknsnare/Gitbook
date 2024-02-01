# 🧜♀ Sysmon

{% embed url="https://tryhackme.com/room/sysmon" %}

Sysmon gathers detailed and high-quality logs as well as event tracing that assists in identifying anomalies in your environment. Sysmon is most commonly used in conjunction with security information and event management (SIEM) system or other log parsing solutions that aggregate, filter, and visualize events. When installed on an endpoint, Sysmon will start early in the Windows boot process.

Events within Sysmon are stored in _`Applications and Services Logs/Microsoft/Windows/Sysmon/Operational`_





## Event IDS

```powershell
Event ID 1: Process Creation
Event ID 3: Network Connection
Event ID 7: Image Loaded
Event ID 8: CreateRemoteThread
Event ID 11: File Created
Event ID 12 / 13 / 14: Registry Event
Event ID 15: FileCreateStreamHash
Event ID 22: DNS Event
```
