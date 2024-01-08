# Nmap Scan Patterns & Summary

```bash
#TCP
tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024 
#SYN
tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024  
#UDP
icmp.type==3 and icmp.code==3  
```



## TCP

Open TCP port (Connect):\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/500bb6902ef6b2edb515bb1828088d82.png" alt=""><figcaption></figcaption></figure>

Closed TCP port (Connect):

![Wireshark - tcp connect scan and closed tcp port](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/c194773203502d659d72706aa93eae59.png)

## SYN

Open TCP port (SYN):

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/0dbf4e7b74ad99f7060241fc37d8d570.png" alt=""><figcaption></figcaption></figure>

Closed TCP port (SYN):

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/488115fed65b69aa95aa2677cf2ae800.png" alt=""><figcaption></figcaption></figure>

## UDP

Closed (port no 69) and open (port no 68) UDP ports:\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/bb88ee3b05687c6ece165ab7e9fe12bf.png" alt=""><figcaption></figcaption></figure>
