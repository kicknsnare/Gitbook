# Summary

```bash
#################### First step #################
Identify the IP address attempting reconnaissance
#Web
stream:http
src_ip
#Example 
index=botsv1 imreallynotbatman.com sourcetype=stream:http
#################### Second Step ################
Validate the IP that is scanning
#Dig into the logs
User-Agent, Post request, URIs, etc
#Dig more:
index=botsv1 imreallynotbatman.com src=40.80.148.42 sourcetype=suricata
#Check for the signature alerts

```

