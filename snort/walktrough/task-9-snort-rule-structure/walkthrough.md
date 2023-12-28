# Walkthrough

Write a rule to filter IP ID "35369" and run it against the given pcap file. What is the request name of the detected packet?&#x20;

```bash
snort -c local.rules -A full -l . -r task9.pcap
cat alert
```

<mark style="color:yellow;">TIMESTAMP REQUEST</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/4473bb32873117a2082c5f43e81c7383ebb88b93eb70d78f552029d799cdcec2/68747470733a2f2f692e696d6775722e636f6d2f4b3768686c35572e6a7067" alt="" width="375"><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/6f1577cd0c1a09488719ecb6536e764ac417cee8ab3194024588091ef205ffbd/68747470733a2f2f692e696d6775722e636f6d2f594f38613667542e6a7067" alt="" width="375"><figcaption></figcaption></figure>

Create a rule to filter packets with Syn flag and run it against the given pcap file. What is the number of detected packets?\
<mark style="color:yellow;">I removed the alert and log generated before</mark>

<mark style="color:yellow;">1</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/ae2487374d924505dc6a743c03797673dfa7fcd5ae8abe18755910b144a6e39a/68747470733a2f2f692e696d6775722e636f6d2f504743445239332e6a7067" alt="" width="375"><figcaption></figcaption></figure>

Clear the previous log and alarm files and deactivate/comment out the old rule.

Write a rule to filter packets with Push-Ack flags and run it against the given pcap file. What is the number of detected packets?

&#x20;

<figure><img src="https://camo.githubusercontent.com/f23391d30a6b25319547fd68b7419444f0cc5e832ca51c9596aaf0e7d75acb78/68747470733a2f2f692e696d6775722e636f6d2f4e3267334245532e6a7067" alt="" width="375"><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/716e9a12962cc1789cfeddbe3445d56ca2315c0fa5da9ffa598c577a16d07992/68747470733a2f2f692e696d6775722e636f6d2f6f48415a736b432e6a7067" alt="" width="188"><figcaption></figcaption></figure>

<mark style="color:yellow;">216</mark>

Clear the previous log and alarm files and deactivate/comment out the old rule.

Create a rule to filter packets with the same source and destination IP and run it against the given pcap file. What is the number of packets that show the same source and destination address?

<figure><img src="https://camo.githubusercontent.com/d952575e8f2f3413c6a2860110f1dfd53009624e6c999976ee7201b81ef6884b/68747470733a2f2f692e696d6775722e636f6d2f6175666b4231742e6a7067" alt=""><figcaption></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/fab7e4f1d72f0f5ce9900fb6c4892f5ab8ec6a6ec9eb370c317a796274c62b49/68747470733a2f2f692e696d6775722e636f6d2f6343716a6c63712e6a7067" alt=""><figcaption></figcaption></figure>

Case Example - An analyst modified an existing rule successfully. Which rule option must the analyst change after the implementation?

<mark style="color:yellow;">rev</mark>
