# Summary

```bash
#Most used commands
snort -c local.rules -A full -l . -r <pcap>
snort -c local.rules -A console -r pcap #doesn't generated alert nor logs
snort -d -r <snort.log>
strings <snort.log>
```

```bash
#Rules filters
#Failed login attempts
content:"530 User"/"530"
#Succesful loging attempts
content:"230 User"/"230"
#failed login attempts with a valid username but a bad password or no password.
content:"331 Password"
#failed login attemps + other filter
content:"Administrator"; content:"331 Password"
#Payload Size
dside:min<>max

#MIME or signature
content: "| |" or content:""
|89 50 4E 47 0D 0A 1A 0A| -> png signature
depth:8 -> #Will limit the search of the packet 
#for the first 8 bytes corresponding to the png signature
content:"GIF89a"; depth:6
```

```bash
#syntax errors
<- #Doesn't exist
[port1,port2] #right way to include port range
-Check protocol
-Check ";"
-Check spaces
```
