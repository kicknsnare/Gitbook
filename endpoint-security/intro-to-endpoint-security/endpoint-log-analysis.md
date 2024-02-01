# 🔍 Endpoint Log Analysis

## Event Correlation

Event correlation identifies significant relationships from multiple log sources such as application logs, endpoint logs, and network logs.

Event correlation deals with identifying significant artefacts co-existing from different log sources and connecting each related artefact.

For example, a network connection log may exist in various log sources such as Sysmon logs (Event ID 3: Network Connection) and Firewall Logs. The Firewall log may provide the source and destination IP, source and destination port, protocol, and the action taken. In contrast, Sysmon logs may give the process that invoked the network connection and the user running the process.

With this information, we can connect the dots of each artefact from the two data sources:

* Source and Destination IP
* Source and Destination Port
* Action Taken
* Protocol
* Process name
* User Account
* Machine Name



## Baselining

Baselining is the process of knowing what is expected to be normal. In terms of endpoint security monitoring, it requires a vast amount of data-gathering to establish the standard behaviour of user activities, network traffic across infrastructure, and processes running on all machines owned by the organization.

| Baseline                                                                                                                                                  | Unusual Activity                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| The organization's employees are in London, and the regular working hours are between 9 AM and 6 PM.                                                      | A user has authenticated via VPN connecting from Singapore at 3 AM.                      |
| A single workstation is assigned to each employee.                                                                                                        | A user has attempted to authenticate to multiple workstations.                           |
| Employees can only access selected websites on their workstations, such as OneDrive, SharePoint, and other O365 applications.                             | A user has uploaded a 3GB file on Google Drive.                                          |
| Only selected applications are installed on workstations, mainly Microsoft Applications such as Microsoft Word, Excel, Teams, OneDrive and Google Chrome. | A process named firefox.exe has been observed running on multiple employee workstations. |

csrss.exe

&#x20;smss.exe

&#x20;wininit.exe

&#x20;winlogon.exe

&#x20;explorer.exe

&#x20;svchost.exe
