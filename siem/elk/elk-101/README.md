# 👊 ELK 101

* How to perform searches, apply a filter, save search.
* How to create visualizations.
* Investigate VPN logs to identify anomalies.
* To create a dashboard using saved searches and visualizations.



{% embed url="https://tryhackme.com/room/investigatingwithelk101" %}

A US-based company **`CyberT`** has been monitoring the VPN logs of the employees, and the SOC team detected some anomalies in the VPN activities. Our task as SOC Analysts is to examine the VPN logs for January 2022 and identify the anomalies. Some of the key points to note before the investigation are:

* All VPN logs are being ingested into the index `vpn_connections`.
* The index contains the VPN logs for January 2022.
* A user `Johny Brown` was terminated on 1st January 2022.
* We observed failed connection attempts against some users that need to be investigated.
