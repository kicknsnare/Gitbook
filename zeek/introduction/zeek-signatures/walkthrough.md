# Walkthrough

```bash
#commands
zeek -C -r http.pcap -s http-password.sig
cat signatures.log | zeek-cut src_addr dst_addr event_msg
cat signatures.log | zeek-cut src_port
cat conn.log | zeek-cut id.orig_p orig_pkts resp_pkts | grep 38706
zeek -C -r ftp.pcap -s ftp-bruteforce.sig
cat notice.log | zeek-cut uid | sort | uniq | wc -l

```

Investigate the http.pcap file. Create the  HTTP signature shown in the task and investigate the pcap. What is the source IP of the first event?\
<mark style="color:green;">10.10.57.178</mark>



<figure><img src="https://camo.githubusercontent.com/050896376b3f901b2a8c6627fcc9a48dc5ecbbdd592381580ab02c67d7e72f43/68747470733a2f2f692e696d6775722e636f6d2f756b5442306b6a2e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/715804e925e7ee90f74a1b004dc155cc920ce16a9449a41ab0c27181148bf3c6/68747470733a2f2f692e696d6775722e636f6d2f594976443459632e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/8a94fe931c8cb1dac9cf4295e96b13891b7446537ef5b78862bea96363f7370a/68747470733a2f2f692e696d6775722e636f6d2f4e4839446b48682e706e67" alt=""><figcaption></figcaption></figure>

What is the source port of the second event?

<mark style="color:green;">38712</mark>



<figure><img src="https://camo.githubusercontent.com/5c5af29103e47ae8d463e0362787b48b7890892d8947b1117c7499fce9078029/68747470733a2f2f692e696d6775722e636f6d2f78314c453374552e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

Investigate the conn.log.\
What is the total number of the sent and received packets from source port 38706?

<mark style="color:green;">20</mark>



<figure><img src="https://camo.githubusercontent.com/bf245667f51e6ebe55957ce8603320f8770ad20acd43fd7e8fba5402d294b12e/68747470733a2f2f692e696d6775722e636f6d2f346747657456382e706e67" alt=""><figcaption></figcaption></figure>

&#x20;





<figure><img src="https://camo.githubusercontent.com/27470141770392d14213824302a827345489381bf521d2e8f5d58cfbf3de1ffa/68747470733a2f2f692e696d6775722e636f6d2f38456d434178492e706e67" alt=""><figcaption></figcaption></figure>

Create the global rule shown in the task and investigate the ftp.pcap file.

Investigate the notice.log. What is the number of unique events?

<mark style="color:green;">1413</mark>



What is the number of ftp-brute signature matches?

<mark style="color:green;">1410</mark>
