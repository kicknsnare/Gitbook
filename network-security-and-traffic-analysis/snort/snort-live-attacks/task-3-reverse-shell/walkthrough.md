# Walkthrough

```bash
#Used Commands:
sudo snort -dev -l .
sudo snort -d -r snort.log.1703884215
```

First of all, start Snort in sniffer mode and try to figure out the attack source, service and port.

Then, write an IPS rule and run Snort in IPS mode to stop the brute-force attack. Once you stop the attack properly, you will have the flag on the desktop!

Here are a few points to remember:

* Create the rule and test it with "-A console" mode.&#x20;
* Use "-A full" mode and the default log path to stop the attack.
* Write the correct rule and run the Snort in IPS "-A full" mode.
* Block the traffic at least for a minute and then the flag file will appear on your desktop.

Stop the attack and get the flag (which will appear on your Desktop)\
<mark style="color:yellow;">THM{0ead8c494861079b1b74ec2380d2cd24}</mark>

```bash
sudo snort -dev -l .
sudo snort -d -r snort.log.1703884215
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/97cf44e280d526b057955ee46e583a6907290e8c01ba1aca1be62065c255f862/68747470733a2f2f692e696d6775722e636f6d2f51646c705564582e706e67" alt=""><figcaption></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/a9802c69bdd087f0331fbd0fd82fc1ce4897842fe428a66aacb9c004741c088f/68747470733a2f2f692e696d6775722e636f6d2f753848623172612e706e67" alt=""><figcaption></figcaption></figure>

&#x20;[![](https://camo.githubusercontent.com/3b3cb88d9051e40a8d3559b8e5312cbfa4513771045c03dd499aad51b4449a9a/68747470733a2f2f692e696d6775722e636f6d2f33735a31434c752e706e67)](https://camo.githubusercontent.com/3b3cb88d9051e40a8d3559b8e5312cbfa4513771045c03dd499aad51b4449a9a/68747470733a2f2f692e696d6775722e636f6d2f33735a31434c752e706e67)

<figure><img src="https://camo.githubusercontent.com/2733730f4299c9a8972d7f18faf828f156bf774011e7b8e060f5eb537c00c706/68747470733a2f2f692e696d6775722e636f6d2f7930474f50616a2e706e67" alt=""><figcaption><p>Suspicious, isn't it?</p></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/f136cfc86a4093fbbcad181b09b1ad36c23913d11cedb9eda564244b3be6e9fe/68747470733a2f2f692e696d6775722e636f6d2f4e7455616c394b2e706e67" alt=""><figcaption><p>I used alert because drop was not giving me any alert </p></figcaption></figure>

```bash
sudo snort -c /etc/snort/snort.conf -q -Q --daq afpacket -i eth0:eth1 -A full
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/5f45a56152089e100887397a6bff4827f8574b01d686f3d58b8af7cea230a423/68747470733a2f2f692e696d6775722e636f6d2f6f6677364a46382e706e67" alt=""><figcaption></figcaption></figure>

What is the used protocol/port in the attack?\
<mark style="color:yellow;">tcp/4444</mark>



Which tool is highly associated with this specific port number?

<mark style="color:yellow;">Metasploit</mark>
