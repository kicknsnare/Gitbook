# ICMP Trafic

This is most commonly used with utilities like ping and traceroute. Below you can see a sample of what a ping would look like, we can see a request to the server from ICMP, then a reply from the server.

![](https://assets.tryhackme.com/additional/wireshark101/icmp/1.png)

## ICMP Request

Important to see the <mark style="color:yellow;">**`type and code of the packet`**</mark>. A type that <mark style="color:yellow;">**`equals 8`**</mark> means that it is a <mark style="color:yellow;">**`request packet`**</mark>, if it is <mark style="color:yellow;">**`equal to 0`**</mark> it is a <mark style="color:yellow;">**`reply packet`**</mark>. <mark style="color:yellow;">**`When these codes are altered or do not seem correct that is typically a sign of suspicious activity.`**</mark>

The timestamp can be useful for identifying the time the ping was requested it can also be useful to identify suspicious activity in some cases.

\


<figure><img src="https://assets.tryhackme.com/additional/wireshark101/icmp/2.png" alt=""><figcaption></figcaption></figure>

## ICMP Reply

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/icmp/3.png" alt=""><figcaption></figcaption></figure>

\
