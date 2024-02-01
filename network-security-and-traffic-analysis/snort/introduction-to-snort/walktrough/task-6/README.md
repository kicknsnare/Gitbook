# Task 6

\


| Parameter | Description                                                                                                                                                                |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -l        | <p>Logger mode, target log and alert output directory. Default output folder is /var/log/snort</p><p>The default action is to dump as tcpdump format in /var/log/snort</p> |
| -K ASCII  | Log packets in ASCII format.                                                                                                                                               |
| -r        | <p>Reading option, read the dumped logs in Snort.<br></p>                                                                                                                  |
| -n        | Specify the number of packets that will process/read. Snort will stop after reading the specified number of packets.                                                       |



## Packet Logger mode

```bash
sudo snort -dev -l . # -l . creates the logs in the current directory
```

Checking the generated logs

```bash
ls .
```



## Logging with -K ASCII

It provides multiple files in a human readable format

```bash
sudo snort -dev -K ASCII -l .
```



## Reading generated logs with -r

```bash
sudo snort -r <name_of_the_file_with_logs>
```

"-r" parameter also allows users to filter the binary log files. You can filter the processed log to see specific packets with the "-r" parameter and Berkeley Packet Filters (BPF).&#x20;

* `sudo snort -r logname.log -X`
* `sudo snort -r logname.log icmp`
* `sudo snort -r logname.log tcp`
* `sudo snort -r logname.log 'udp and port 53'`

The output will be the same as the above, but only packets with the chosen protocol will be shown. Additionally, you can specify the number of processes with the parameter "-n". The following command will process only the first 10 packets:\
\
&#x20;`snort -dvr logname.log -n 10`
