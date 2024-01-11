# Encrypted Protocol Analysis: Decrypting HTTPS



## Decrypting HTTPS



Additional information for HTTPS :\


| Notes                                                                                                                                                                                                                                                                                                                                                                | Wireshark Filter                                                                                                                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>"HTTPS Parameters" for grabbing the low-hanging fruits:</p><ul><li>Request: Listing all requests<br></li><li>TLS: Global TLS search</li><li>TLS Client Request</li><li>TLS Server response</li><li>Local Simple Service Discovery Protocol (SSDP)</li></ul><p>Note: SSDP is a network protocol that provides advertisement and discovery of network services.</p> | <ul><li><code>http.request</code></li></ul><ul><li><code>tls</code></li></ul><ul><li><code>tls.handshake.type == 1</code></li></ul><ul><li><code>tls.handshake.type == 2</code></li></ul><ul><li><code>ssdp</code></li></ul> |

Similar to the TCP three-way handshake process, the TLS protocol has its handshake process. The first two steps contain "Client Hello" and "Server Hello" messages. The given filters show the initial hello packets in a capture file. These filters are helpful to spot which IP addresses are involved in the TLS handshake.\


* Client Hello: `(http.request or tls.handshake.type == 1) and !(ssdp)`&#x20;
* Server Hello:`(http.request or tls.handshake.type == 2) and !(ssdp)` &#x20;



## IMPORTANT

An encryption key log file is a text file that contains unique key pairs to decrypt the encrypted traffic session. These key pairs are automatically created (per session) when a connection is established with an SSL/TLS-enabled webpage. As these processes are all accomplished in the browser, you need to configure your system and use a suitable browser (Chrome and Firefox support this) to save these values as a key log file. To do this, you will need to set up an environment variable and create the SSLKEYLOGFILE, and the browser will dump the keys to this file as you browse the web. SSL/TLS key pairs are created per session at the connection time, so it is important to dump the keys during the traffic capture. Otherwise, it is not possible to create/generate a suitable key log file to decrypt captured traffic. <mark style="color:yellow;">**`You can use the "right-click" menu or "Edit --> Preferences --> Protocols --> TLS" menu to add/remove key log files.`**</mark>

Adding key log files with the "right-click" menu:\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/17b1557ea94f23b7a9c6851fddbd366b.png" alt=""><figcaption></figcaption></figure>

Adding key log files with the "Edit --> Preferences --> Protocols --> TLS" menu:

![Wireshark - https adding keylogfile to decrypt https traffic step-2](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/7461f414bdc9926827dd54d57e7a8825.png)

