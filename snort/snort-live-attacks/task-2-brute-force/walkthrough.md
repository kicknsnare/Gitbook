# Walkthrough

```bash
#notes
Service: ssh Port: 22 Protocol: TCP
```

```bash
#Used commands:
sudo snort -d -n 20
sudo snort -c local.rules -A console

#Setting snort as IPS -Q --daq afpacket
sudo snort -c /etc/snort/snort.conf -q -Q --daq afpacket -i eth0:eth1 -A full

```

First of all, start Snort in sniffer mode and try to figure out the attack source, service and port.\


Then, write an IPS rule and run Snort in IPS mode to stop the brute-force attack. Once you stop the attack properly, you will have the flag on the desktop!

Here are a few points to remember:

* Create the rule and test it with "-A console" mode.&#x20;
* Use "-A full" mode and the default log path to stop the attack.
* Write the correct rule and run the Snort in IPS "-A full" mode.
* Block the traffic at least for a minute and then the flag file will appear on your desktop.\


Stop the attack and get the flag (which will appear on your Desktop)

THM{81b7fef657f8aaa6e4e200d616738254}

**`Let's identify the service, protocol, and port`**

```bash
sudo snort -d -n 20
```





&#x20;**`Let's create the rule:`**

<figure><img src="https://camo.githubusercontent.com/d81eb99eaff7769d4be6739cde05401e5281517b210f1ffb2589c2247829f1a1/68747470733a2f2f692e696d6775722e636f6d2f5a457150686e672e706e67" alt=""><figcaption></figcaption></figure>

**`Lets test our rule:`**

```bash
sudo snort -c local.rules -A console
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/a2ee4a421fcf8dd14831dd8e2d9c19e3cbaedaf7ae0bc1440eb91a38c98d03d8/68747470733a2f2f692e696d6775722e636f6d2f626a535a3956552e706e67" alt=""><figcaption></figcaption></figure>

**`Snort in IPS Mode`**&#x20;

We should get the flag

```bash
sudo snort -c /etc/snort/snort.conf -q -Q --daq afpacket -i eth0:eth1 -A full
```

What is the name of the service under attack?

&#x20;ssh



What is the used protocol/port in the attack?

tcp/22\
