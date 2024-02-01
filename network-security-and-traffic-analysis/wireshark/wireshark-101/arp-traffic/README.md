# ARP Traffic

**`ARP is one of the simpler protocols to analyze, all you need to remember is to identify whether it is a request or reply packet and who it is being sent by.`**&#x20;

\


ARP or Address Resolution Protocol is a Layer 2 protocol that is used to connect IP Addresses with MAC Addresses. They will contain REQUEST messages and RESPONSE messages. To identify packets the message header will contain one of two operation codes:

* Request (1)
* Reply (2)

It is useful to note that most devices will identify themselves or Wireshark will identify it such as Intel\_78, <mark style="color:yellow;">**`an example of suspicious traffic would be many requests from an unrecognized source.`**</mark>

## ARP Request Packets

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/23.png" alt=""><figcaption><p>Looking at the packet details above, the most important details of the packet are outlined in red.</p></figcaption></figure>

## ARP Reply Packets

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/24.png" alt=""><figcaption><p>Looking at the above packet details we can see from the Opcode that it is an ARP Reply packet</p></figcaption></figure>

\


