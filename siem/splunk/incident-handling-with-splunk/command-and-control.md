# Command and Control

Command and Control:

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/f346d2d7b7628eaeddf45d5c14c5b54a.png" alt=""><figcaption></figcaption></figure>

The attacker uploaded the file to the server before defacing it. While doing so, the attacker used a Dynamic DNS to resolve a malicious IP. Our objective would be to find the IP that the attacker decided the DNS.

To investigate the communication to and from the adversary's IP addresses, we will be examining the network-centric log sources mentioned above. We will first pick fortigate\_utm to review the firewall logs and then move on to the other log sources.

Search Query: `index=botsv1 sourcetype=fortigate_utm"poisonivy-is-coming-for-you-batman.jpeg"`\
\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/a2df650b7d76e7cc7a795b8d0b627bfe.png" alt=""><figcaption></figcaption></figure>

&#x20;

Looking into the Fortinet firewall logs, we can see the src IP, destination IP, and URL. Look at the fields on the left panel and the field `url` contains the FQDN (Fully Qualified Domain Name).

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/e5cda837fe7a7cbfa791515b49756f69.png" alt=""><figcaption></figcaption></figure>

Though we have found the answer, we can verify other log sources.\


Let us verify the answer by looking at another log source.`stream:http`.

Search Query: `index=botsv1 sourcetype=stream:http dest_ip=23.22.63.114 "poisonivy-is-coming-for-you-batman.jpeg" src_ip=192.168.250.70`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/495918ac13b99ae950a0ac470fa349fc.png" alt=""><figcaption></figcaption></figure>

We have identified the suspicious domain as a Command and Control Server, which the attacker contacted after gaining control of the server.\


Note: We can also confirm the domain by looking at the last log source `stream:dns` to see what DNS queries were sent from the webserver during the infection period.
