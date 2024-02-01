# HTTPS TRAFFIC

<mark style="color:yellow;">**`You can use an RSA key in Wireshark in order to view the data unencrypted. In order to load an RSA key navigate to Edit > Preferences > Protocols > TLS > [+] . SSL for older versions`**</mark>

. If you are using an older version of Wireshark then this will be SSL instead of TLS.&#x20;

Before sending encrypted information the client and server need to agree upon various steps in order to make a secure tunnel.

1. Client and server agree on a protocol version
2. Client and server select a cryptographic algorithm
3. The client and server can authenticate to each other; this step is optional
4. Creates a secure tunnel with a public key

We can begin analyzing HTTPS traffic by looking at packets for the handshake between the client and the server. Below is a Client Hello packet showing the SSLv2 Record Layer, Handshake Type, and SSL Version.

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/39.png" alt=""><figcaption></figcaption></figure>

Below is the Server Hello packet sending similar information as the Client Hello packet however this time it includes session details and SSL certificate information\


![](https://assets.tryhackme.com/additional/wireshark101/40.png)

Below is the Client Key Exchange packet, this part of the handshake will determine the public key to use to encrypt further messages between the Client and Server.

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/41.png" alt=""><figcaption></figcaption></figure>

In the next packet, the server will confirm the public key and create the secure tunnel, all traffic after this point will be encrypted based on the agreed-upon specifications listed above.

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/41.png" alt=""><figcaption></figcaption></figure>

The traffic between the Client and the Server is now encrypted and you will need the secret key in order to decrypt the data stream being sent between the two hosts.

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/42.png" alt=""><figcaption></figcaption></figure>

