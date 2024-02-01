# Walkthrough

Investigate the mx-1.pcap file with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l . -r mx-1.pcap`

What is the number of the generated alerts?

<mark style="color:yellow;">170</mark>

&#x20;[![](https://camo.githubusercontent.com/33c1a0c7663a58c35c994088c1396477ecf0a3611b58b3944a8709fff0c498de/68747470733a2f2f692e696d6775722e636f6d2f4b4c6d7a6b53712e6a7067)](https://camo.githubusercontent.com/33c1a0c7663a58c35c994088c1396477ecf0a3611b58b3944a8709fff0c498de/68747470733a2f2f692e696d6775722e636f6d2f4b4c6d7a6b53712e6a7067)

Keep reading the output. How many TCP Segments are Queued?

<mark style="color:yellow;">18</mark>

&#x20;[![](https://camo.githubusercontent.com/c1ae678127ffef3b6aaa906619749232fd21792b168676d5cdfb6877c0d1e2d2/68747470733a2f2f692e696d6775722e636f6d2f423332315052482e6a7067)](https://camo.githubusercontent.com/c1ae678127ffef3b6aaa906619749232fd21792b168676d5cdfb6877c0d1e2d2/68747470733a2f2f692e696d6775722e636f6d2f423332315052482e6a7067)

Keep reading the output.How many "HTTP response headers" were extracted?

<mark style="color:yellow;">3</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/2ebe950fb46b941070047641530aa02dbe729480d2da150371b1ab00569f2ada/68747470733a2f2f692e696d6775722e636f6d2f58654675576c672e6a7067" alt=""><figcaption></figcaption></figure>

Investigate the mx-1.pcap file with the second configuration file.\


`sudo snort -c /etc/snort/snortv2.conf -A full -l . -r mx-1.pcap`

What is the number of the generated alerts?

<mark style="color:yellow;">68</mark>

&#x20;[![](https://camo.githubusercontent.com/f0c17a81e844fe00fdaf650211a5e235def730341a4d371ff57cc992d26c0497/68747470733a2f2f692e696d6775722e636f6d2f716a7947536d4c2e6a706767)](https://camo.githubusercontent.com/f0c17a81e844fe00fdaf650211a5e235def730341a4d371ff57cc992d26c0497/68747470733a2f2f692e696d6775722e636f6d2f716a7947536d4c2e6a706767)

Investigate the mx-2.pcap file with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l . -r mx-2.pcap`

What is the number of the generated alerts?

<mark style="color:yellow;">340</mark>

Keep reading the output. What is the number of the detected TCP packets?

<mark style="color:yellow;">82</mark>

[![](https://camo.githubusercontent.com/9d5c17a92d3590603e98de62abe44507dadb1d332b90acde05f1f50746261984/68747470733a2f2f692e696d6775722e636f6d2f7a5671666b51352e6a7067)](https://camo.githubusercontent.com/9d5c17a92d3590603e98de62abe44507dadb1d332b90acde05f1f50746261984/68747470733a2f2f692e696d6775722e636f6d2f7a5671666b51352e6a7067)

Investigate the mx-2.pcap and mx-3.pcap files with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l . --pcap-list="mx-2.pcap mx-3.pcap"`

What is the number of the generated alerts?

<mark style="color:yellow;">1020</mark>
