# Walkthrough

```bash
#Commands that I used
snort -d -r snort.log.1703809612
```

Let's create IDS Rules for torrent metafiles in the traffic!Answer the questions below

Navigate to the task folder.

Use the given pcap file.

**`Write a rule to detect the torrent metafile in the given pcap.`**

&#x20;What is the number of detected packets?

<mark style="color:yellow;">2</mark>

From the hint: **`Torrent metafiles have a common name extension (.torrent). Try to filter the given pattern in the TCP traffic.`**

&#x20;

<figure><img src="https://camo.githubusercontent.com/694ff23be6d46cfcea8591d5cbb7842ea72ebc5173d89f76e29009cb605a2e39/68747470733a2f2f692e696d6775722e636f6d2f384f614a4966682e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/501f5132ccb1cdb96bf4e95ec87bf6dfc164e57664fab0a42fc6d3b41d852ec4/68747470733a2f2f692e696d6775722e636f6d2f6c4570466279642e706e67" alt=""><figcaption></figcaption></figure>



Investigate the log/alarm files.

**`What is the name of the torrent application?`**

&#x20;[![](https://camo.githubusercontent.com/1a730aef5f041fe1212c4db7d25ef7d1827d32b8ec8d80d7ef2c6ce90356c3e2/68747470733a2f2f692e696d6775722e636f6d2f61506d437143772e706e67)](https://camo.githubusercontent.com/1a730aef5f041fe1212c4db7d25ef7d1827d32b8ec8d80d7ef2c6ce90356c3e2/68747470733a2f2f692e696d6775722e636f6d2f61506d437143772e706e67)

<mark style="color:yellow;">BitTorrent</mark>

Investigate the log/alarm files.

**`What is the MIME (Multipurpose Internet Mail Extensions) type of the torrent metafile?`**

```bash
snort -d -r snort.log.1703809612
```

<mark style="color:yellow;">application/x-bittorrent</mark>

&#x20;[![](https://camo.githubusercontent.com/4630a739413acf7151be30000a793a3e7c9a6b291ff1f7823f63093f9c4a96ea/68747470733a2f2f692e696d6775722e636f6d2f4a59374b3948362e706e67)](https://camo.githubusercontent.com/4630a739413acf7151be30000a793a3e7c9a6b291ff1f7823f63093f9c4a96ea/68747470733a2f2f692e696d6775722e636f6d2f4a59374b3948362e706e67)



Investigate the log/alarm files.

**`What is the hostname of the torrent metafile?`**

<mark style="color:yellow;">tracker2.torrentbox.com</mark>

&#x20;[![](https://camo.githubusercontent.com/52d15457029814a484afc166d825d3e090b90ce5d821ebb181871c04ded0d45d/68747470733a2f2f692e696d6775722e636f6d2f774241666875562e706e67)](https://camo.githubusercontent.com/52d15457029814a484afc166d825d3e090b90ce5d821ebb181871c04ded0d45d/68747470733a2f2f692e696d6775722e636f6d2f774241666875562e706e67)

