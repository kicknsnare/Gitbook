# Walkthrough

```bash
#Commands
zkg list
zeek -Cr http.pcap /opt/zeek/share/zeek/site/zeek-sniffpass
cat notice.log | head
cat notice.log | zeek-cut msg | sort -nr | uniq -c
zeek -Cr case2.pcap /opt/zeek/share/zeek/site/geoip-conn/
cat conn.log | zeek-cut geo.resp.city id.resp_h
```

```bash
#Important recall
#Calling from path
zeek -Cr http.pcap /opt/zeek/share/zeek/site/zeek-sniffpass
#Calling with package name
zeek -Cr http.pcap zeek-sniffpass

```

\
Investigate the http.pcap file with the zeek-sniffpass module. Investigate the notice.log file. Which username has more module hits?\
<mark style="color:green;">BroZeek</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/aa56f99f91d8f9297557963ea5e81c1d2f901981e80bb85a263e5d300eb623d2/68747470733a2f2f692e696d6775722e636f6d2f4d794e767a46572e706e67" alt=""><figcaption></figcaption></figure>

```bash
cat notice.log | zeek-cut msg | sort -nr | uniq -c
```

Investigate the case2.pcap file with geoip-conn module. Investigate the conn.log file. What is the name of the identified City?\
<mark style="color:green;">Chicago</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/2bb1e034e7a7ce3e79d52d79b2ecbb5d08ba5dc1de17d6eac123fcd8fc5321f2/68747470733a2f2f692e696d6775722e636f6d2f564546544a726a2e706e67" alt=""><figcaption></figcaption></figure>

Which IP address is associated with the identified City?\
<mark style="color:green;">23.77.86.54</mark>

```bash
cat conn.log | zeek-cut geo.resp.city id.resp_h
```

Investigate the case2.pcap file with sumstats-counttable.zeek script. How many types of status codes are there in the given traffic capture?\
<mark style="color:green;">4</mark>\


<figure><img src="https://camo.githubusercontent.com/a894240abf0e29ee18c676d2f68ed92b0e20e72073655dd3cd3a807468bc0ba6/68747470733a2f2f692e696d6775722e636f6d2f4a3273694b30592e706e67" alt=""><figcaption></figcaption></figure>
