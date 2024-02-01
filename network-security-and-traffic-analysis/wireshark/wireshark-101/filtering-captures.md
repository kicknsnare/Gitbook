# Filtering Captures

{% embed url="https://www.wireshark.org/docs/wsug_html_chunked/ChWorkBuildDisplayFilterSection.html" %}

## Operators

* <mark style="color:blue;">and - operator</mark>: **`and / &&`**
* <mark style="color:blue;">or - operator</mark>: **`or / ||`**
* <mark style="color:blue;">equals - operator:</mark> **`eq / ==`**
* <mark style="color:blue;">not equal - operator:</mark> **`ne / !=`**
* <mark style="color:blue;">greater than - operator:</mark> **`gt /  >`**
* <mark style="color:blue;">less than - operator:</mark> **`lt / <`**

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
