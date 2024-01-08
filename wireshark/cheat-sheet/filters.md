# Filters

{% embed url="https://www.wireshark.org/docs/wsug_html_chunked/ChWorkBuildDisplayFilterSection.html" %}

## Operators

* <mark style="color:blue;">and - operator</mark>: **`and / &&`**
* <mark style="color:blue;">or - operator</mark>: **`or / ||`**
* <mark style="color:blue;">equals - operator:</mark> **`eq / ==`**
* <mark style="color:blue;">not equal - operator:</mark> **`ne / !=`**
* <mark style="color:blue;">greater than - operator:</mark> **`gt /  >`**
* <mark style="color:blue;">less than - operator:</mark> **`lt / <`**

## Applying filters based on specific things

You can drag and drop something of interest to the filters's tab

## Basic Filtering

The basic syntax of Wireshark filters is some kind of service or protocol like ip or tcp, followed by a dot then whatever is being filtered for example an address, MAC, SRC, protocol, etc.

```bash
#IP
ip.addr == <IP Address>
#Filtering by SRC and DST:
ip.src == <SRC IP Address> and ip.dst == <DST IP Address> 
#Filtering by TCP Protocols:
tcp.port == <Port NUM> or <Protocol Name>
#Filtering by UDP Protocols:
udp.port == <Port NUM> or <Protocol Name>
#Filtering by packet number
frame.number== <number>
#ARP 1= request 2= reply
arp.opcode== 1 | arp.opcode == 2
#MAC address
eth.src == <MAC> 
eth.dst == <MAC>
eth.addr == <MAC>
```

```bash
####################################################################
IP FILTERS
####################################################################
#Show all IP packets.
ip
#Show all packets containing IP address 10.10.10.111.
ip.addr == 10.10.10.111
#Show all packets containing IP addresses from 10.10.10.0/24 subnet.
ip.addr == 10.10.10.0/24
#Show all packets originated from 10.10.10.111
ip.src == 10.10.10.111
#Show all packets sent to 10.10.10.111
ip.dst == 10.10.10.111
#TTL
ip.ttl...

```

```bash
##################################################################
TCP and UDP Filters
##################################################################
#Show all TCP/UDP packets with port 80 
tcp.port == 80 | udp.port == 53
#Show all TCP/UDP packets originating from port 1234
tcp.srcport == 1234 | udp.srcport == 1234
#Show all TCP/UDP packets sent to port 80
tcp.dstport == 80 | udp.dstport == 5353

```

```bash
###############################################################
Application Level Protocol Filters | HTTP and DNS
################################################################
#Show all HTTP packets
http
#how all packets with HTTP response code "200"
http.response.code == 200
#Show all HTTP GET requests
http.request.method == "GET"
#Show all HTTP POST requests
http.request.method == "POST"
#http and port filter example
http.request.method == "GET" and tcp.port== 80
#Show all DNS packets
dns
#Show all DNS requests
dns.flags.response == 0
#Show all DNS responses
dns.flags.response == 1
#Show all DNS "A" records
dns.qry.type == 1
```

## Advanced Filtering

```bash
#Contain Filter
http.server contains "Apache" <- Keyword
#Matches Filter (it is case insensitive)
http.host matches "\.(php|html)" <- regular expression 
#In filter
tcp.port in {80 443 8080} <- scope/range
#filtering port range
udp.dstport >=55 and udp.dstport <=70 #from 55 to 70
#Upper and lower Filter
upper(http.server) contains "APACHE" #Find all "APACHE" servers.
lower(http.server) contains "apache" #Find all "apache" servers.
#String 
string(frame.number) matches "[13579]$" #Find all frames with odd numbers
even == "[02468]$"

```

## Nmap Scans

```bash
#TCP
tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024 
#SYN
tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024  
#UDP
icmp.type==3 and icmp.code==3  
```



## ARP Poisoning

<pre class="language-bash"><code class="lang-bash"><strong>#ARP 
</strong>arp
#ARP requests
arp.opcode == 1
#ARP responses
arp.opcode == 2
#ARP Scanning
arp.dst.hw_mac==00:00:00:00:00:00
#Possible ARP poisoning detection
arp.duplicate-address-detected or arp.duplicate-address-frame
#Possible ARP flooding from detection:
((arp) &#x26;&#x26; (arp.opcode == 1)) &#x26;&#x26; (arp.src.hw_mac == target-mac-address)
</code></pre>
