# Task 2 Writing IDS Rules HTTP

```bash
#Commands that I used:
snort -c local.rules -A full -l . -r mx-3.pcap
snort -r snort.log.1703793603 -n 63
snort -r snort.log.1703793603 -n 62
snort -r snort.log.1703793603 -n 64
snort -r snort.log.1703793603 -n 65
```

Use the given pcap file.\


Write rules to detect "all TCP port 80 traffic" packets in the given pcap file.&#x20;

What is the number of detected packets?

Note: You must answer this question correctly before answering the rest of the questions in this task.

<mark style="color:yellow;">328</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/773ef4dd00c3848cbd8f9db10ff6478b4a9ee4f1fdbd6f1fc2abcfb6683eff6d/68747470733a2f2f692e696d6775722e636f6d2f564c316a7931632e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/285873744bb065e02b9736eea7652564dfa5b10ddfb6139ebf3a934a863a0e6a/68747470733a2f2f692e696d6775722e636f6d2f36446a4c3350792e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log file.\


What is the destination address of packet 63?

<mark style="color:yellow;">145.254.160.237</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/94728cd5439845591eeb322e75893b8de94714cbdef39f2d04b2edb006fcaafa/68747470733a2f2f692e696d6775722e636f6d2f74676f776c794f2e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log file.

&#x20;What is the ACK number of packet 64?

<mark style="color:yellow;">0x38AFFFF3</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/6b0cd153e78cb022c51aba3f9de96c773596a4462a76952a6f44e3b9b9b51b7a/68747470733a2f2f692e696d6775722e636f6d2f7847374e4964492e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log file.\


What is the SEQ number of packet 62?

<mark style="color:yellow;">0x38AFFFF3</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/426c5e9cf5d55d3a710bb00552d3998c8712cbd03979918c9404248ebd668744/68747470733a2f2f692e696d6775722e636f6d2f7849656e4b56682e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log file.\


What is the TTL of packet 65?



<mark style="color:yellow;">128</mark>

Investigate the log file.\


What is the source IP of packet 65?



<mark style="color:yellow;">145.254.160.237</mark>

Investigate the log file.\


What is the source port of packet 65?



<mark style="color:yellow;">3372</mark>



&#x20;

<figure><img src="https://camo.githubusercontent.com/7fdf2ca64b2e6b2f358a3a1c38725d2fdf877be56d0e0de6b4d663d4d0d8ef2f/68747470733a2f2f692e696d6775722e636f6d2f7a4f656f3668552e706e67" alt=""><figcaption></figcaption></figure>
