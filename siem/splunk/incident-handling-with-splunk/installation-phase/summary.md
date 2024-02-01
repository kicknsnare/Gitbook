# Summary

```bash
#HTTP traffic that contains .exe or any uploaded malicious file
index=botsv1 sourcetype=stream:http dest_ip="192.168.250.70" *.exe
field-> filename
part_filename{}
#Prove that the files came from the attacker's IPs
c_ip
#Prove that the file was executed on the server
index=botsv1 "<filename>"
#For the evidence of execution, we can leverage sysmon and look at the EventCode=1 for program execution.
index=botsv1 "3791.exe" sourcetype="XmlWinEventLog" EventCode=1
#Check Command Line Field

```

