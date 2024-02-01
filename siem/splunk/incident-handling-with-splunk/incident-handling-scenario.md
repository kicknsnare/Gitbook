# Incident Handling: Scenario

In this exercise, we will investigate a cyber attack in which the attacker defaced an organization's website. This organization has Splunk as a SIEM solution setup. Our task as a Security Analysis would be to investigate this cyber attack and map the attacker's activities into all 7 of the Cyber Kill Chain Phases. It is important to note that we don't need to follow the sequence of the cyber kill chain during the Investigation. One finding in one phase will lead to another finding that may have mapped into some other phase.

## Cyber Kill Chain

We will follow the Cyber kill Chain Model and map the attacker's activity in each phase during this Investigation. When required, we will also utilize Open Source Intelligence (OSINT) and other findings to fill the gaps in the kill chain. It is not necessary to follow this sequence of the phases while investigating.

* Reconnaissance
* Weaponization
* Delivery
* Exploitation
* Installation
* Command & Control
* Actions on Objectives

\


Scenario

A Big corporate organization Wayne Enterprises has recently faced a cyber-attack where the attackers broke into their network, found their way to their web server, and have successfully defaced their website http://www.imreallynotbatman.com. Their website is now showing the trademark of the attackers with the message YOUR SITE HAS BEEN DEFACED as shown below.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/dcc528c218e8dda78504f55f58188575.png)\


They have requested "**US**" to join them as a **Security Analyst** and help them investigate this cyber attack and find the root cause and all the attackers' activities within their network.

\


The good thing is, that they have Splunk already in place, so we have got all the event logs related to the attacker's activities captured. We need to explore the records and find how the attack got into their network and what actions they performed.\


This Investigation comes under the `Detection and Analysis phase.`

Splunk

During our investigation, we will be using `Splunk` as our SIEM solution. Logs are being ingested from webserver/firewall/Suricata/Sysmon etc. In the data summary tab, we can explore the log sources showing visibility into both network-centric and host-centric activities. To get the complete picture of the hosts and log sources being monitored in Wayne Enterprise, please click on the Data summary and navigate the available tabs to get the information.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/dc5ec747ef4b0f3eada2aac0bb1fa0ed.gif" alt=""><figcaption></figcaption></figure>

Interesting log Sources\


Some of the interesting log sources that will help us in our Investigation are:\


| <p>Log Sources      <br></p>      | <p>Details                                                                                                                                                                                                                                    <br></p>                                                                               |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>wineventlog    <br></p>        | <p>It contains Windows Event logs                                                                                                                                                                                                                                                                                           <br></p> |
| <p>winRegistry           <br></p> | <p>It contains the logs related to registry creation / modification / deletion etc.                                                                                               <br></p>                                                                                                                                           |
| <p>XmlWinEventLog<br></p>         | <p>It contains the sysmon event logs. It is a very important log source from an investigation point of view.                                                                            <br></p>                                                                                                                                     |
| <p>fortigate_utm<br></p>          | It contains Fortinet Firewall logs                                                                                                                                                                                                                                                                                                   |
| <p>iis<br></p>                    | <p>It contains IIS web server logs                                                                                                                                                                                       <br></p>                                                                                                    |
| <p>Nessus:scan<br></p>            | <p>It contains the results from the Nessus vulnerability scanner.                                                                                                                             <br></p>                                                                                                                               |
| <p>Suricata<br></p>               | <p>It contains the details of the alerts from the Suricata IDS.   This log source shows which alert was triggered and what caused the alert to get triggered— a very important log source for the Investigation.                                                                                            <br></p>                 |
| <p>stream:http<br></p>            | <p>It contains the network flow related to http traffic.                                                                                                                                               <br></p>                                                                                                                      |
| <p>stream: DNS<br></p>            | It contains the network flow related to DNS traffic.                                                                                                                                                                                                                                                                                 |
| <p>stream:icmp<br></p>            | <p>It contains the network flow related to icmp traffic.                                                                                                                                                                                      <br></p>                                                                               |

\


Note: All the event logs that we are going to investigate are present in `index=botsv1`\
