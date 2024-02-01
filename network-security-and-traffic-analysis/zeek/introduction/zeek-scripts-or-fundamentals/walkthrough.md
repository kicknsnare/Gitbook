# Walkthrough

```bash
#Commands
zeek -C -r smallFlows.pcap dhcp-hostname.zeek
cat dhcp.log | grep fields
zeek -C -r bigFlows.pcap dhcp-hostname.zeek | sort -nr | uniq | wc -l
```

Investigate the smallFlows.pcap file. Investigate the dhcp.log file. What is the domain value of the "vinlap01" host?\
<mark style="color:green;">astaro\_vineyard</mark>



<figure><img src="https://camo.githubusercontent.com/4eb72b8c7c3eb4c7cedd0f23ed5a1a3245e20899b8c573f844c32b97ae1228a9/68747470733a2f2f692e696d6775722e636f6d2f7231747032327a2e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/efac4cd2d0043a16bc40766d3c3aa48019a952dc974388efa7e1260229ff88d5/68747470733a2f2f692e696d6775722e636f6d2f62676e3951346a2e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

Investigate the bigFlows.pcap file. Investigate the dhcp.log file. What is the number of identified unique hostnames?\
<mark style="color:green;">17</mark>



<figure><img src="https://camo.githubusercontent.com/085988dc113f007dc28dbfbdecc0157bbe712ad04a654831f3dc19d14cf36356/68747470733a2f2f692e696d6775722e636f6d2f557257634538522e706e67" alt=""><figcaption></figcaption></figure>

Investigate the dhcp.log file. What is the identified domain value?\
<mark style="color:green;">jaalam.net</mark>

```bash
cat dhcp.log | zeek-cut domain | sort -r | uniq
```

\
