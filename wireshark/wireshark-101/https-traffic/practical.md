# Practical

In order to load an RSA key navigate to Edit > Preferences > Protocols > TLS > \[+]

IP Address: 127.0.0.1

Port: start\_tls

Protocol: http

Keyfile: RSA key location



<figure><img src="https://camo.githubusercontent.com/d283723dbe74c1cf7ed4a91a0d48df0488a2a946e7f6cf62991ed0267eef8739/68747470733a2f2f692e696d6775722e636f6d2f69366b4d5a4e582e706e67" alt=""><figcaption></figcaption></figure>

Now that we have an RSA key imported into Wireshark, if we go back to the packet capture we can see that the data stream is now unencrypted.

<figure><img src="https://assets.tryhackme.com/additional/wireshark101/46.png" alt=""><figcaption></figcaption></figure>

We can now see the HTTP requests in unencrypted data streams. Looking further at one of the details of the packet we can see the unencrypted data stream closer. \


<figure><img src="https://assets.tryhackme.com/additional/wireshark101/47.png" alt=""><figcaption></figcaption></figure>

Looking at the packet details we can see some very important information such as the request URI and the User-Agent which can be very useful in practical applications of Wireshark such as threat hunting and network administration.

We can now use other features in order to organize the data stream, like using the export HTTP object feature, to access this feature navigate to File > Export Objects > HTTP

![](https://assets.tryhackme.com/additional/wireshark101/48.png)
