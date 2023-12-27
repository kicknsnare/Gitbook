# Important information

| Parameter | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -c        | Defining the configuration file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -T        | Testing the configuration file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| -N        | <p>Disable logging.<br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| -D        | <p>Background mode.<br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| -A        | <p>Alert modes;<br></p><p>full: Full alert mode, providing all possible information about the alert. This one also is the default mode; once you use -A and don't specify any mode, snort uses this mode.</p><p>fast:  Fast mode shows the alert message, timestamp, source and destination IP, along with port numbers.</p><p>console: Provides fast style alerts on the console screen.</p><p>cmg: CMG style, basic header details with payload in hex and text format.</p><p>none: Disabling alerting.</p> |

Once you start running IDS/IPS mode, you need to use rules. As we mentioned earlier, we will use a pre-defined ICMP rule as an example. The defined rule will only generate alerts in any direction of ICMP packet activity.

`alert icmp any any <> any any  (msg: "ICMP Packet Found"; sid: 100001; rev:1;)`

This rule is located in "/etc/snort/rules/local.rules".

## IDS/IPS mode with parameter "-c and -T"

```bash
sudo snort -c /etc/snort/snort.conf -T
```

You will see a "Snort successfully validated the configuration!"



## Note

You will have to execute the traffic-generator first in order to work

## IDS/IPS mode with parameter "-N"

```bash
sudo snort -c /etc/snort/snort.conf -N
```

## IDS/IPS mode with parameter "-D"

```bash
sudo snort -c /etc/snort/snort.conf -D
ps -ef | grep snort #to show the corresponding processes
```

## IDS/IPS mode with parameter "-A"

```bash
sudo snort -c /etc/snort/snort.conf -A
```

## IDS/IPS mode with parameter "-A console, cmg, fast, full, none."

```bash
sudo snort -c /etc/snort/snort.conf -A console
sudo snort -c /etc/snort/snort.conf -A cmg
sudo snort -c /etc/snort/snort.conf -A fast
sudo snort -c /etc/snort/snort.conf -A full
sudo snort -c /etc/snort/snort.conf -A none
```

## Checking Processes

```bash
ps -ef | grep snort
```

## IPS mode and dropping packets

Snort IPS mode activated with `-Q --daq afpacket` parameters. You can also activate this mode by editing snort.conf file.

Activate the Data Acquisition (DAQ) modules and use the afpacket module to use snort as an IPS: `-i eth0:eth1`

```bash
sudo snort -c /etc/snort/snort.conf -q -Q --daq afpacket -i eth0:eth1 -A console
```
