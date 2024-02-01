# TCP Traffic

Below you can see a sample of a Nmap scan, scanning port 80 and 443. We can tell that the port is closed due to the RST, ACK packet in red.

![](https://assets.tryhackme.com/additional/wireshark101/25.png)

Typically when this handshake is out of order or when it includes other packets like an RST packet, something suspicious or wrong is happening in the network.



## TCP Packet Analysis

&#x20;The main thing that we want to look for when looking at a TCP packet is the <mark style="color:yellow;">**`sequence number and acknowledgment number.`**</mark>

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/27.png" alt=""><figcaption></figcaption></figure>

In this case, we see that the port was not open because the acknowledgment number is 0.&#x20;

Within Wireshark, we can also see the original sequence number by navigating to edit > preferences > protocols > TCP > relative sequence numbers (uncheck boxes).

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/28.png" alt=""><figcaption></figcaption></figure>

![](https://assets.tryhackme.com/additional/wireshark101/29.png)
