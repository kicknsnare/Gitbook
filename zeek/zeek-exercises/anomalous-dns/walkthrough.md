# Walkthrough

```bash
#commands
zeek -Cr dns-tunneling.pcap 
cat dns.log | head
cat dns.log | zeek-cut qtype_name | grep "AAAA" | wc -l
cat conn.log | zeek-cut duration | sort -n | uniq
cat dns.log | zeek-cut query |rev | cut -d '.' -f 1-2 | sort -nr | uniq
cat conn.log | zeek-cut id.orig_h id.resp_h
```

Investigate the dns-tunneling.pcap file. Investigate the dns.log file. What is the number of DNS records linked to the IPv6 address?\
Hint: DNS "AAAA" records store IPV6 addresses.

<mark style="color:green;">320</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/202180fdd208e11c1366a83728986f7696a88ae7fed97538ca2a895db5ee83b6/68747470733a2f2f692e696d6775722e636f6d2f6b424f3165716f2e706e67" alt=""><figcaption></figcaption></figure>

Investigate the **conn.log** file. What is the longest connection duration?\
<mark style="color:green;">9.420791</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/fe22b6615c844afbcca2dd508ca9a3255d042393786650b4ab90e5c4c49e5d9a/68747470733a2f2f692e696d6775722e636f6d2f6f726835386a412e706e67" alt=""><figcaption></figcaption></figure>

Investigate the **dns.log** file. Filter all unique DNS queries. What is the number of unique domain queries?\
<mark style="color:green;">6</mark>

```bash
cat dns.log | zeek-cut query |rev | cut -d '.' -f 1-2 | sort -nr | uniq
```

There are a massive amount of DNS queries sent to the same domain. This is abnormal. Let's find out which hosts are involved in this activity. Investigate the **conn.log** file. What is the IP address of the source host?\
<mark style="color:green;">10.20.57.3</mark>

\


<figure><img src="https://camo.githubusercontent.com/1d336eff1984664639f6cc0b7696697826d093fd69125879ca2389d085a44b5f/68747470733a2f2f692e696d6775722e636f6d2f715359464c6c312e706e67" alt=""><figcaption></figcaption></figure>
