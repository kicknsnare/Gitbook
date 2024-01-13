# Email Delivery

## Ports

{% embed url="https://help.dreamhost.com/hc/en-us/articles/215612887-Email-client-protocols-and-port-numbers" %}

Secure Transport for SMTP&#x20;

* 465

Secure Transport for IMAP

* 993

Secure Transport for POP3

* 995



There are 3 specific protocols involved to facilitate the outgoing and incoming email messages, and they are briefly listed below.

* SMTP (Simple Mail Transfer Protocol) - It is utilized to handle the sending of emails.&#x20;
* POP3 (Post Office Protocol) - Is responsible transferring email between a client and a mail server.&#x20;
* IMAP (Internet Message Access Protocol) - Is responsible transferring email between a client and a mail server.&#x20;



## POP3 and IMAP Difference

* POP3 emails can only be downloaded, stored and acessed from a single device, and the emails don't get stored in the server unless you have enable this options
* IMAP messages are stored in the server, can be sync and accessed from multiple devices

![](https://assets.tryhackme.com/additional/phishing1/email-network-flow-4.png)

Alexa writes the email and after she is done she presses send, it goes to the SMPT Server, but the server needs to know where to send the email so it goes to the DNS Server. The DNS Server send back the information and the SMTP server sends the email accross the internet, going through multiple SMPT servers to the final SMTP server where the email waits until billy (the receiver ) logs in and hit the new emails inbox to download the email
