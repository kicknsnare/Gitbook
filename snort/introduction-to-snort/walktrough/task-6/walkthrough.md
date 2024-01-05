# Walkthrough

\
Investigate the traffic with the default configuration file with ASCII mode.\


`sudo snort -dev -K ASCII -l .`

&#x20;

<figure><img src="https://camo.githubusercontent.com/6643cd61c49a68994436d1c8186c8cee01f9570548be2e12c3e7a352ed61cae6/68747470733a2f2f692e696d6775722e636f6d2f64734c5a37394d2e6a7067" alt=""><figcaption></figcaption></figure>

Execute the traffic generator script and choose "TASK-6 Exercise". Wait until the traffic ends, then stop the Snort instance. Now analyse the output summary and answer the question.

`sudo ./traffic-generator.sh`

&#x20;

<figure><img src="https://camo.githubusercontent.com/0a5acdddb7c12fe695acb97ed1e0a3bfaa8612e5340efaf9748f596b951f7240/68747470733a2f2f692e696d6775722e636f6d2f514a316f6239412e6a7067" alt="" width="375"><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/58d2b96de58504a4ac279a063e9ba3905ef6eb0f9b421708ede9fd53cb92905e/68747470733a2f2f692e696d6775722e636f6d2f6b71524d47616a2e6a7067" alt=""><figcaption></figcaption></figure>

Now, you should have the logs in the current directory. Navigate to folder "145.254.160.237". What is the source port used to connect port 53?&#x20;

<mark style="color:yellow;">3009</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/4efb34d92340fbad041215fdaa613727fc71793ace8230be769bfec197107d0f/68747470733a2f2f692e696d6775722e636f6d2f556a6f333155572e6a7067" alt=""><figcaption></figcaption></figure>

Use snort.log.1640048004 \


Read the snort.log file with Snort; what is the IP ID of the 10th packet?

`snort -r snort.log.1640048004 -n 10`

&#x20;

<figure><img src="https://camo.githubusercontent.com/13147969ebcc743599297fe4fdc0ba2ca7ea889dc27d900811c2c789fea9ec03/68747470733a2f2f692e696d6775722e636f6d2f6f34583330705a2e6a7067" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/cfd15ad8472a4378ad8c0345478e7bdfb395be7c7cc66e5fd03890038a698004/68747470733a2f2f692e696d6775722e636f6d2f6d6f516d5468482e6a7067" alt=""><figcaption></figcaption></figure>

<mark style="color:yellow;">49313</mark>



Read the "snort.log.1640048004" file with Snort; what is the referer of the 4th packet?\
&#x20;

<figure><img src="https://camo.githubusercontent.com/c185325e5669d25652c9a261ceef111b862c4f064b0a2fd162fa3ed3dbd0ede3/68747470733a2f2f692e696d6775722e636f6d2f366745573651472e6a7067" alt=""><figcaption></figcaption></figure>

[ ](http://www.ethereal.com/development.html)[<mark style="color:yellow;">http://www.ethereal.com/development.html</mark>](http://www.ethereal.com/development.html)

Read the "snort.log.1640048004" file with Snort; what is the Ack number of the 8th packet?\
&#x20;

<figure><img src="https://camo.githubusercontent.com/878d7cd88e11b07615fc7252d99aa0692a1baeb7f916af85c51d0c56436c615f/68747470733a2f2f692e696d6775722e636f6d2f6e795630476b532e6a7067" alt=""><figcaption></figcaption></figure>

&#x20;<mark style="color:yellow;">0x38AFFFF3</mark>

Read the "snort.log.1640048004" file with Snort; what is the number of the "TCP port 80" packets?

```bash
sudo snort -r snort.log.1640048004 'tcp and port 80'
```

<mark style="color:yellow;">41</mark>

[![](https://camo.githubusercontent.com/47e8b715106fa2ff59165a95ab66fdb7b95f23ca9c7d35baf5364143911e1ed6/68747470733a2f2f692e696d6775722e636f6d2f673178384547572e706e67)](https://camo.githubusercontent.com/47e8b715106fa2ff59165a95ab66fdb7b95f23ca9c7d35baf5364143911e1ed6/68747470733a2f2f692e696d6775722e636f6d2f673178384547572e706e67)

