# Network Security Monitoring and Zeek

## Network Monitoring

Watch/contiuosly the network traffic for further investigation. This action aims to detect and reduce network problems



## Zeek Architecture

Zeek has two primary layers; "Event Engine" and "Policy Script Interpreter". The Event Engine layer is where the packets are processed; it is called the event core and is responsible for describing the event without focusing on event details. It is where the packages are divided into parts such as source and destination addresses, protocol identification, session analysis and file extraction. The Policy Script Interpreter layer is where the semantic analysis is conducted. It is responsible for describing the event correlations by using Zeek scripts.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/07d58ecdaa53829df19be1ec47d2d666.png)



## Zeek default log path

**`/opt/zeek/logs/`**

## Zeek as service

The only way to listen to the live network traffic is using Zeek as a service

```bash
status
start
stop
#You can also use the "ZeekControl" mode with the following commands as well;
zeekctl status
zeekctl start 
zeekctl stop 
```



## Zeek control mode

```bash
zeekctl
```

## Zeek packet investigator

```bash
zeek -C -r sample.pcap 
```

| Parameter | Description                                |
| --------- | ------------------------------------------ |
| -r        |  Reading option, read/process a pcap file. |
| -C        |  Ignoring checksum errors.                 |
| -v        |  Version information.                      |
| zeekctl   | ZeekControl module.                        |

