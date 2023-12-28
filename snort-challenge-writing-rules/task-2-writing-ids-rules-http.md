# Task 2 Writing IDS Rules HTTP

```bash
#Commands that I used:
snort -c local.rules -A full -l . -r mx-3.pcap
```

Use the given pcap file.\


Write rules to detect "all TCP port 80 traffic" packets in the given pcap file.&#x20;

What is the number of detected packets?

Note: You must answer this question correctly before answering the rest of the questions in this task.

<mark style="color:yellow;">328</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/773ef4dd00c3848cbd8f9db10ff6478b4a9ee4f1fdbd6f1fc2abcfb6683eff6d/68747470733a2f2f692e696d6775722e636f6d2f564c316a7931632e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log file.\


What is the destination address of packet 63?



<mark style="color:yellow;">145.254.160.237</mark>

Investigate the log file.\


&#x20;What is the ACK number of packet 64?



<mark style="color:yellow;">0x38AFFFF3</mark>

Investigate the log file.\


What is the SEQ number of packet 62?



<mark style="color:yellow;">0x38AFFFF3</mark>

Investigate the log file.\


What is the TTL of packet 65?



<mark style="color:yellow;">128</mark>

Investigate the log file.\


What is the source IP of packet 65?



<mark style="color:yellow;">145.254.160.237</mark>

Investigate the log file.\


What is the source port of packet 65?



<mark style="color:yellow;">3372</mark>
