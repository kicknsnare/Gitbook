# Nmap Scans RAW



| Notes                                                                                                           | Wireshark Filters                                                                                                            |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Global search.                                                                                                  | <ul><li><code>tcp</code></li></ul><ul><li><code>udp</code></li></ul>                                                         |
| <ul><li>Only SYN flag.</li><li>SYN flag is set. The rest of the bits are not important.</li></ul>               | <ul><li><code>tcp.flags == 2</code></li></ul><ul><li><code>tcp.flags.syn == 1</code></li></ul>                               |
| <ul><li>Only ACK flag.</li><li>ACK flag is set. The rest of the bits are not important.<br></li></ul>           | <ul><li><code>tcp.flags == 16</code></li></ul><ul><li><code>tcp.flags.ack == 1</code></li></ul>                              |
| <ul><li>Only SYN, ACK flags.</li><li>SYN and ACK are set. The rest of the bits are not important.</li></ul>     | <ul><li><code>tcp.flags == 18</code></li></ul><ul><li><code>(tcp.flags.syn == 1) and (tcp.flags.ack == 1)</code></li></ul>   |
| <ul><li>Only RST flag.</li><li>RST flag is set. The rest of the bits are not important.<br></li></ul>           | <p><br></p><ul><li><code>tcp.flags == 4</code></li></ul><ul><li><code>tcp.flags.reset == 1</code></li></ul>                  |
| <ul><li>Only RST, ACK flags.</li><li>RST and ACK are set. The rest of the bits are not important.<br></li></ul> | <ul><li><code>tcp.flags == 20</code></li></ul><ul><li><code>(tcp.flags.reset == 1) and (tcp.flags.ack == 1)</code></li></ul> |
| <ul><li>Only FIN flag</li><li>FIN flag is set. The rest of the bits are not important.</li></ul>                | <ul><li><code>tcp.flags == 1</code></li></ul><ul><li><code>tcp.flags.fin == 1</code></li></ul>                               |



## TCP Connect Scans

<mark style="color:yellow;">**`nmap -sT`**</mark>

TCP flags in a nutshell.

* Relies on the three-way handshake (needs to finish the handshake process).
* Usually has a windows size larger than 1024 bytes as the request expects some data due to the nature of the protocol.

| Open TCP Port                                                           | <p>Open TCP Port<br></p>                                                                     | <p>Closed TCP Port<br></p>                              |
| ----------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| <ul><li>SYN --></li><li>&#x3C;-- SYN, ACK</li><li>ACK --><br></li></ul> | <ul><li>SYN --></li><li>&#x3C;-- SYN, ACK</li><li>ACK --></li><li>RST, ACK --><br></li></ul> | <ul><li>SYN --></li><li>&#x3C;-- RST, ACK<br></li></ul> |

Open TCP port (Connect):\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/500bb6902ef6b2edb515bb1828088d82.png" alt=""><figcaption></figcaption></figure>

Closed TCP port (Connect):

![Wireshark - tcp connect scan and closed tcp port](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/c194773203502d659d72706aa93eae59.png)

<mark style="color:yellow;">**`tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024`**</mark>&#x20;

![Wireshark - tcp connect scan pattern](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/7025561839f99201724629fae1274f2d.png)



## SYN Scans

<mark style="color:yellow;">**`nmap -sS`**</mark>

TCP SYN Scan in a nutshell:

* Doesn't rely on the three-way handshake (no need to finish the handshake process).
* Usually have a size less than or equal to 1024 bytes as the request is not finished and it doesn't expect to receive data.

| Open TCP Port                                                     | Close TCP Port                                     |
| ----------------------------------------------------------------- | -------------------------------------------------- |
| <ul><li>SYN --></li><li>&#x3C;-- SYN,ACK</li><li>RST--></li></ul> | <ul><li>SYN --></li><li>&#x3C;-- RST,ACK</li></ul> |

Open TCP port (SYN):

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/0dbf4e7b74ad99f7060241fc37d8d570.png" alt=""><figcaption></figcaption></figure>

Closed TCP port (SYN):

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/488115fed65b69aa95aa2677cf2ae800.png" alt=""><figcaption></figcaption></figure>

<mark style="color:yellow;">**`tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024`**</mark> &#x20;

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/d033bde6ee753f070678cc56665d79fa.png" alt=""><figcaption></figcaption></figure>

## UDP Scans

<mark style="color:yellow;">**`nmap -sU`**</mark>

* Doesn't require a handshake process
* No prompt for open ports
* ICMP error message for close ports

| <p>Open UDP Port<br></p>         | <p>Closed UDP Port<br></p>                                                                                        |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| <ul><li>UDP packet --></li></ul> | <ul><li>UDP packet --></li><li>ICMP Type 3, Code 3 message. (Destination unreachable, port unreachable)</li></ul> |

Closed (port no 69) and open (port no 68) UDP ports:\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/bb88ee3b05687c6ece165ab7e9fe12bf.png" alt=""><figcaption></figcaption></figure>

The above image shows that the closed port returns an ICMP error packet.

Once you expand the ICMP section in the packet details pane, you will see the encapsulated data and the original request, as shown in the below image.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/0e63fe522554f08810d7d60b8a331ae7.png" alt=""><figcaption></figcaption></figure>

\


**`icmp.type==3 and icmp.code==3`** &#x20;

![Wireshark - udp port scan pattern](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/626988e40598f6190c81f59ab3ff813c.png)
