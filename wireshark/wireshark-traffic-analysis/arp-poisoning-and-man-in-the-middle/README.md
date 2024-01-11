# ARP Poisoning & MAn in The Middle

**ARP** protocol, or **A**ddress **R**esolution **P**rotocol (**ARP**), is the technology responsible for allowing devices to identify themselves on a network. Address Resolution Protocol Poisoning (also known as ARP Spoofing or Man In The Middle (MITM) attack) is a type of attack that involves network jamming/manipulating by sending malicious ARP packets to the default gateway. The ultimate aim is to manipulate the "IP to MAC address table" and sniff the traffic of the target host.

* Common patterns are request & response, announcement and gratuitous packets.

| Notes                                                                                                                                                                                                                                                             | Wireshark filter                                                                                                                                                                                                                                                                                                                                                                  |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Global search                                                                                                                                                                                                                                                     | <ul><li><code>arp</code></li></ul>                                                                                                                                                                                                                                                                                                                                                |
| <p>"ARP" options for grabbing the low-hanging fruits:</p><ul><li>Opcode 1: ARP requests.</li><li>Opcode 2: ARP responses.</li><li>Hunt: Arp scanning</li><li>Hunt: Possible ARP poisoning detection</li><li>Hunt: Possible ARP flooding from detection:</li></ul> | <ul><li><code>arp.opcode == 1</code></li></ul><ul><li><code>arp.opcode == 2</code></li></ul><ul><li><code>arp.dst.hw_mac==00:00:00:00:00:00</code></li></ul><ul><li><code>arp.duplicate-address-detected or arp.duplicate-address-frame</code></li></ul><ul><li><code>((arp) &#x26;&#x26; (arp.opcode == 1)) &#x26;&#x26; (arp.src.hw_mac == target-mac-address)</code></li></ul> |

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/ef02b6b0434491aea9eb6957c70c32d2.png" alt=""><figcaption></figcaption></figure>

identifying the malicious packet from the legitimate one is the analyst's challenge. A possible IP spoofing case is shown in the picture below.

![Wireshark - arp spoof](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/7f0e92a248da129dda0593a299ecb368.png)

| Notes                                     | <p>Detection Notes<br></p>                                                                                                            | Findings                                                                   |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| <p>Possible IP address match.<br></p>     | <p>1 IP address announced from a MAC address.<br></p>                                                                                 | <ul><li>MAC: 00:0c:29:e2:18:b4</li><li>IP: 192.168.1.25</li></ul>          |
| <p>Possible ARP spoofing attempt.<br></p> | <p>2 MAC addresses claimed the same IP address (192.168.1.1).<br>The " 192.168.1.1" IP address is a possible gateway address.<br></p> | <ul><li>MAC1: 50:78:b3:f3:cd:f4</li><li>MAC 2: 00:0c:29:e2:18:b4</li></ul> |
| <p>Possible ARP flooding attempt.<br></p> | <p>The MAC address that ends with "b4" claims to have a different/new IP address.<br></p>                                             | <ul><li>MAC: 00:0c:29:e2:18:b4</li><li>IP: 192.168.1.1</li></ul>           |

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/e02a42c9d4e3f17a94acbae4cacb6b65.png" alt=""><figcaption></figcaption></figure>

There is a new anomaly; the MAC address that ends with "b4" crafted multiple ARP requests with the "192.168.1.25" IP address

| <p>Possible ARP flooding attempt.<br></p> | The MAC address that ends with "b4" crafted multiple ARP requests against a range of IP addresses. | <ul><li>MAC: 00:0c:29:e2:18:b4</li><li>IP: 192.168.1.xxx</li></ul> |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |

![Wireshark - arp spoof mitm http view-1](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/f55ebc1632f6776e074dc29842221b48.png)

There is HTTP traffic, and everything looks normal at the IP level, so there is no linked information with our previous findings. Let's add the MAC addresses as columns in the packet list pane to reveal the communication behind the IP addresses.\


![2](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/f885817e77449e6898ba3ede164723c4.png)

One more anomaly! The MAC address that ends with "b4" is the destination of all HTTP packets! It is evident that there is a MITM attack, and the attacker is the host with the MAC address that ends with "b4". All traffic linked to "192.168.1.12" IP addresses is forwarded to the malicious host. Let's summarise the findings before concluding the investigation. &#x20;

| IP to MAC matches.        | 3  IP to MAC address matches.                           | <ul><li>MAC: 00:0c:29:e2:18:b4 = IP: 192.168.1.25</li><li>MAC: 50:78:b3:f3:cd:f4 = IP: 192.1681.1</li><li>MAC: 00:0c:29:98:c7:a8 = IP: 192.168.1.12</li></ul> |
| ------------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Attacker                  | <p>The attacker created noise with ARP packets.<br></p> | <ul><li>MAC: 00:0c:29:e2:18:b4 = IP: 192.168.1.25<br></li></ul>                                                                                               |
| <p>Router/gateway<br></p> | <p>Gateway address.<br></p>                             | <ul><li>MAC: 50:78:b3:f3:cd:f4 = IP: 192.1681.1<br></li></ul>                                                                                                 |
| <p>Victim<br></p>         | The attacker sniffed all traffic of the victim.         | <ul><li>MAC: 50:78:b3:f3:cd:f4 = IP: 192.1681.12</li></ul>                                                                                                    |
