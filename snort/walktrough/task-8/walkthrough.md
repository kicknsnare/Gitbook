# Walkthrough

Investigate the mx-1.pcap file with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l . -r mx-1.pcap`

What is the number of the generated alerts?

<mark style="color:yellow;">170</mark>

Keep reading the output. How many TCP Segments are Queued?

<mark style="color:yellow;">18</mark>

Keep reading the output.How many "HTTP response headers" were extracted?

<mark style="color:yellow;">3</mark>

Investigate the mx-1.pcap file with the second configuration file.\


`sudo snort -c /etc/snort/snortv2.conf -A full -l . -r mx-1.pcap`

What is the number of the generated alerts?

<mark style="color:yellow;">68</mark>

Investigate the mx-2.pcap file with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l . -r mx-2.pcap`

What is the number of the generated alerts?

<mark style="color:yellow;">340</mark>

Keep reading the output. What is the number of the detected TCP packets?

<mark style="color:yellow;">82</mark>

Investigate the mx-2.pcap and mx-3.pcap files with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l . --pcap-list="mx-2.pcap mx-3.pcap"`

What is the number of the generated alerts?

<mark style="color:yellow;">1020</mark>
