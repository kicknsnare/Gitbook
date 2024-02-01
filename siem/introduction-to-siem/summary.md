# Summary



## Host-Centric Logs

Logs that happen in the endpoint like powershell exucution, a user accesing a file, a user attempting to authenticate...



## Network-centric Logs

Logs that an endoint or host create by accesing the network, ssh connection, web traffic, vpns





## Windows Simple

Event Viewer

## Linux

* /var/log/httpd : Contains HTTP Request  / Response and error logs.
* /var/log/cron   : Events related to cron jobs are stored in this location.
* /var/log/auth.log and /var/log/secure : Stores authentication related logs.
* /var/log/kern : This file stores kernel related events.
* /var/log/apache or /var/log/httpd Web server (Important)



## Event IDS for important Events

Clear log -> 104

Process execution activity -> 4688

Rule: If the Log source is WinEventLog AND EventID is 104 - Trigger an alert `Event Log Cleared`

Rule: If Log Source is WinEventLog AND EventCode is 4688, and NewProcessName contains whoami, then Trigger an ALERT `WHOAMI command Execution DETECTED`
