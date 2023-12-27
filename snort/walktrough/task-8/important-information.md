# Important Information

Reading a pcap without using any additional parameters we discussed before will only overview the packets and provide statistics about the file. In most cases, this is not very handy. We are investigating the pcap with Snort to benefit from the rules and speed up our investigation process by using the known patterns of threats.

| Parameter           | Description                                       |
| ------------------- | ------------------------------------------------- |
| -r / --pcap-single= | Read a single pcap                                |
| --pcap-list=""      | Read pcaps provided in command (space separated). |
| --pcap-show         | Show pcap name on console during processing.      |



## Investigating single PCAP with parameter -r

```bash
sudo snort -c /etc/snort/snort.conf -q -r icmp-test.pcap -A console -n 10
```

You will have to move to the TASK-8 directory

## Investigating multiple PCAPs with parameter --pcap-list

```bash
sudo snort -c /etc/snort/snort.conf -q --pcap-list="icmp-test.pcap http2.pcap" -A console -n 10
```



## Investigating multiple PCAPs with parameter "--pcap-show"

```bash
sudo snort -c /etc/snort/snort.conf -q --pcap-list="icmp-test.pcap http2.pcap" -A console --pcap-show
```
