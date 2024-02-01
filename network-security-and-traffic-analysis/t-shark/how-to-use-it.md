# How to use it



## Pretty basic for now

```bash
################# Tshark Commands ###################
#Reading a file
tshark -r dns.cap
#Counting how many packets
tshark -r dns.cap | wc -l
#filtering -Y
tshark -r dns.cap -Y "dns.qry.type == 1" 
#Extracting specific field values -T fields -e [filename]
tshark -r dns.cap -Y "dns.qry.type == 1" -T fields -e dns.qry.name 

```

NOTE: An easy way to identify field names in Wireshark is to navigate to the Packet Details in the capture, highlight the interesting field, then view the bottom left corner.

![](https://i.imgur.com/Ki9lou5.png)
