# Walkthrough 2

\
&#x20;

<figure><img src="https://camo.githubusercontent.com/84cfe47ecf45b88592ff1e97cab4c3db5362098c30a6623a5cc630dfb519590c/68747470733a2f2f692e696d6775722e636f6d2f73544643554a622e706e67" alt=""><figcaption><p>ANSWER 1-2</p></figcaption></figure>

How many packets are in this capture?\
<mark style="color:green;">125</mark>

How many DNS queries are in this pcap? (Not responses!)\
<mark style="color:green;">56</mark>

What is the DNS transaction ID of the suspicious queries (in hex)?\


<figure><img src="https://camo.githubusercontent.com/be9e0f87ba5c6c6b115f909d041aa3c6f9ef52758265cae35b75046e6f856e62/68747470733a2f2f692e696d6775722e636f6d2f61766741344e432e706e67" alt=""><figcaption></figcaption></figure>

What is the string extracted from the DNS queries?\


```bash
tshark -r dnsexfil.pcap -Y "dns.flags.response == 0" | grep -oP '[A-Za-z0-9]+(?=\.m4lwhere\.org)' | tr -d '\n' | awk '{print}'

```

<figure><img src="https://camo.githubusercontent.com/806467fc801f2f460d156c8bd31db513310898329a285bde655b4f127de926d4/68747470733a2f2f692e696d6775722e636f6d2f5670574f76584d2e706e67" alt=""><figcaption></figcaption></figure>

What is the flag?

<figure><img src="https://camo.githubusercontent.com/8cde9a08f687716192acbcbddd2234249e4af00310a687110d0eda94d5b44f4d/68747470733a2f2f692e696d6775722e636f6d2f64466a41457a792e706e67" alt=""><figcaption></figcaption></figure>
