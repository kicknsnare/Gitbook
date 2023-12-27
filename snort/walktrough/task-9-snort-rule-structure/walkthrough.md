# Walkthrough

Write a rule to filter IP ID "35369" and run it against the given pcap file. What is the request name of the detected packet?&#x20;

```bash
snort -c local.rules -A full -l . -r task9.pcap
cat alert
```

<mark style="color:yellow;">TIMESTAMP REQUEST</mark>

Create a rule to filter packets with Syn flag and run it against the given pcap file. What is the number of detected packets?\
<mark style="color:yellow;">I removed the alert and log generated before</mark>

<mark style="color:yellow;">1</mark>

Clear the previous log and alarm files and deactivate/comment out the old rule.

Write a rule to filter packets with Push-Ack flags and run it against the given pcap file. What is the number of detected packets?



Clear the previous log and alarm files and deactivate/comment out the old rule.

Create a rule to filter packets with the same source and destination IP and run it against the given pcap file. What is the number of packets that show the same source and destination address?



Case Example - An analyst modified an existing rule successfully. Which rule option must the analyst change after the implementation?

