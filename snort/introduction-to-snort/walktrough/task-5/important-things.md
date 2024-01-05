# Important Things

## Flags

| Parameter | Description                                                                                                                                                    |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -v        | Verbose. Display the TCP/IP output in the console.                                                                                                             |
| -d        | <p>Display the packet data (payload).<br></p>                                                                                                                  |
| -e        | <p>Display the link-layer (TCP/IP/UDP/ICMP) headers. <br></p>                                                                                                  |
| -X        | Display the full packet details in HEX.                                                                                                                        |
| -i        | This parameter helps to define a specific network interface to listen/sniff. Once you have multiple interfaces, you can choose a specific interface to sniff.  |



## Sniffing with parameter -i

```bash
sudo snort -v -i eth0
```



## Sniffing with parameter -v

```bash
sudo snort -v
```

## Sniffing with parameter -d

```bash
sudo snort -d
```

## Sniffing with parameter -de

```bash
sudo snort -de
```

## Sniffing with parameter -X

```bash
sudo snort -X
```
