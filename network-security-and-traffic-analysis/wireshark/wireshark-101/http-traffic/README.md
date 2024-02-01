# HTTP Traffic

HTTP is one of the most straight forward protocols for packet analysis, the protocol is straight to the point and does not include any handshakes or prerequisites before communication.

\
<mark style="color:yellow;">**`Some of the important information we can gather from the packet is the Request URI, File Data, Server.`**</mark>

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/33.png" alt=""><figcaption></figcaption></figure>

<mark style="color:yellow;">**`Protocol Hierarchy`**</mark>

&#x20;Navigate to Statistics > Protocol Hierarchy.

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/36.png" alt=""><figcaption></figcaption></figure>

This information can be very useful in practical applications like threat hunting to identify discrepancies in packet captures.



<mark style="color:yellow;">**`Organizing the Request URIs with Export HTTP Object`**</mark>

To use Export HTTP Object navigate to file > Export Objects > HTTP.\


![](https://assets.tryhackme.com/additional/wireshark101/37.png)

<mark style="color:yellow;">**`Organizing Endpoints and IPs with Endpoints`**</mark>

&#x20;To use the Endpoints feature navigate to Statistics > Endpoints.

![](https://assets.tryhackme.com/additional/wireshark101/38.png)
