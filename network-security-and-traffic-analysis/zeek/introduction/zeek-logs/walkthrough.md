# Walkthrough

```bash
#commands
zeek -C -r <file>
cat dhcp.log | zeek-cut host_name
cat dns.log | zeek-cut query | uniq
cat conn.log | zeek-cut duration| sort -n -r
```

\
Investigate the **sample.pcap** file. Investigate the dhcp.log file. What is the available hostname?\
<mark style="color:green;">Microknoppix</mark>



<figure><img src="https://camo.githubusercontent.com/d6dce951140566653878c4fe00d3312763b4c065fd438596727eedea8b083d22/68747470733a2f2f692e696d6775722e636f6d2f565a386266524b2e706e67" alt=""><figcaption></figcaption></figure>

Investigate the **dns**.log file. What is the number of unique DNS queries?\
<mark style="color:green;">2</mark>

<figure><img src="https://camo.githubusercontent.com/deabc5be79c73eba0351e95e3fb94941be2c36a3208a800e31a0d9e24b003c6f/68747470733a2f2f692e696d6775722e636f6d2f4d75626756746b2e706e67" alt=""><figcaption></figcaption></figure>



Investigate the **conn.log** file. What is the longest connection duration?\
<mark style="color:green;">332.319364</mark>

<figure><img src="https://camo.githubusercontent.com/5b53436af239bab7c5e0daede9541a99d714e3d1408425e2b2ba7e9e740be204/68747470733a2f2f692e696d6775722e636f6d2f5666666c4e746e2e706e67" alt=""><figcaption></figcaption></figure>



\
