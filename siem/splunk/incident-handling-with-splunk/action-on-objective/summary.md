# Summary

```bash
#What caused Defacement?
Examine suricata logs and the addresses communicating with the webserver
index=botsv1 dest=192.168.250.70 sourcetype=suricata
dest = webserver
#Check if any communication originates from the server
Usually, the web servers do not originate the traffic. 
The browser or the client would be the source
----------------------------------------------------
index=botsv1 src=192.168.250.70 sourcetype=suricata
```

