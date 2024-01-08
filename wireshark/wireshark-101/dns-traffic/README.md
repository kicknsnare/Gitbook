# DNS Traffic

There are a couple of things outlined below that you should keep in the back of your mind when analyzing DNS packets.

* Query-Response
* DNS-Servers Only
* UDP

<mark style="color:yellow;">**`If anyone of these is out of place then the packets should be looked at further and should be considered suspicious.`**</mark>



## DNS Query

Where the query is originating from (UDP 53) <mark style="color:yellow;">**`if it was TCP 53 then it should be considered suspicious traffic`**</mark>

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/31.png" alt=""><figcaption></figcaption></figure>

## DNS Response

It includes and answer that can be used to verify the query

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/32.png" alt=""><figcaption></figcaption></figure>
